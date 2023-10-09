<template>
  <div class="redirect w-full bg-white min-h-screen">
    <h2 class="redirect__heading text-2xl font-bold">Redirect Notice</h2>
    <div class="redirect__description">
      <div class="redirect__description__content">
        <p class="break-words text-sm md:text-lg">
          The page you were on is trying to send you to
        </p>
        <div class="lg:w-4/5">
            <a :href="itemDetails.url" class="cursor-pointer  underline text-blue-700 text-xs md:text-sm break-words">
                https://podcasts.google.com/feed/aHR0cHM6Ly9icmVuZG9uYnVyY2hhcmQubGlic3luLmNvbS9yc3M/episode/NDMwOWVmM2MtNjM3Ni0xMWVkLWI5YWItZTdkYmJhMjdhODkz?sa=X&ved=0CAgQuIEEahgKEwiA3sLX7dX7AhUAAAAAHQAAAAAQgAE
            </a>
        </div>
      </div>
      <div
        class="redirect__description__content lg:mt-8"
      >
        <p class="text-sm md:text-lg">
          The below Video is suggested to you because your Skill/Behavior
          development priority is set with tags:
          <span
            class="tag flex items-center flex-wrap mt-3"
          >
            <span
              class="tag__text text-xs font-semibold mr-2 mb-2"
              v-for="(tag, index) in itemDetails.tags"
              :key="index"
              >#{{ tag }}</span
            >
            &nbsp;
          </span>
        </p>
      </div>
      <div
        class="course__content lg:mt-10 flex align-start"
      >
        <div
          class="course-img relative flex items-center justify-center mb-4 md:mb-0"
        >
          <img
            class="w-full h-full object-cover rounded-md"
            src="@/assets/images/redirect-page/podcast.png"
            @error="randomFeedImage(itemDetails)"
          />
          <div
            class="absolute flex items-center justify-center"
          >
            <img
              v-if="itemDetails.format === 'WATCH'"
              class="img__logo"
              src="@/assets/images/redirect-page/play.svg"
              alt="WATCH"
            />
            <img
              v-else-if="itemDetails.format === 'LISTEN'"
              class="img__logo"
              :src="require(`@/assets/images/redirect-page/headphone.svg`)"
              alt="LISTEN"
            />
          </div>
        </div>
        <div class="details">
          <div class="details__title flex item-start">
            <img
              src="@/assets/images/redirect-page/logo.png"
              :alt="itemDetails.source ? itemDetails.source : 'GetBoarded'"
              @error="altSrcImage"
              class="mr-2"
            />
            <p class="text-sm md:text-base font-semibold">Google Podcasts</p>
            <!-- <p>{{ itemDetails.source }}</p> -->
          </div>
          <div class="details__heading flex items-start">
            <h4 class="clip-text font-bold text-lg md:text-2xl mr-3">
                Why specializing early doesn't always mean career success
                <!-- {{ itemDetails.title }} -->
            </h4>
            <img
              class="details__logo cursor-pointer mt-2"
              src="@/assets/images/redirect-page/soft.svg"
            />
          </div>
          <div class="details__text text-justify clip-text clip-text-3">
            <p class="text-sm md:text-base">
                Making decisions in business can be difficult when you know that your decisions can impact money, revenue or even people's livelihoods. Decision making for people who are naturally indecisive can be even harder. In this episode, we will go over some practical things that you can use for making
            </p>
          </div>
        </div>
      </div>
      <div class="redirect__description__content lg:mt-10">
        <p class="text-xs md:text-lg">
          You can rate the relevance of the content suggestion and the content
          quality from the web page or the email you came for.
        </p>
        <p class="text-xs md:text-lg" v-if="count === 0">Redirecting...</p>
        <p class="text-xs md:text-lg mt-2 md:mt-3" v-else>This page will redirect itself in {{ count }} seconds.</p>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      itemDetails: {
        tags:[
            "Sound Decision Maker",
            "Demonstrating Good Judgement",
            "Constant Learner"
        ],
        format: "WATCH",
        url: "https://podcasts.google.com/feed/aHR0cHM6Ly9icmVuZG9uYnVyY2hhcmQubGlic3luLmNvbS9yc3M/episode/NDMwOWVmM2MtNjM3Ni0xMWVkLWI5YWItZTdkYmJhMjdhODkz?sa=X&ved=0CAgQuIEEahgKEwiA3sLX7dX7AhUAAAAAHQAAAAAQgAE"
      },
      count: 5,
      source: "Google Podcasts",
      title: "Why specializing early doesn't always mean career success",
    };
  },
  mounted() {
    this.getItemById();
  },
  methods: {
    reverseTimeCounter() {
      setInterval(() => {
        this.count = this.count >= 1 ? this.count - 1 : 0;
      }, 1000);
    },
    getItemById() {
      const { itemId, type, gbuid, gborgid, redirectsourceid } =
        this.$route.query;
      this.$store
        .dispatch("library/getItemById", {
          itemId,
          type,
          gbuid,
        })
        .then((res) => {
          this.itemDetails = res;
          if (
            this.itemDetails?.status === "do" &&
            redirectsourceid !== "ORG_REVIEW"
          ) {
            this.$store.dispatch("library/updateItemStatus", {
              getboardedId: gbuid,
              itemId: itemId,
              type: this.itemDetails.type,
              status: "doing",
            });
          }

          this.$store.dispatch("library/postItemAnalytics", {
            gtbrddOrganizationId: gborgid,
            gtbrddUserId: gbuid,
            feedItemId: itemId,
            source: redirectsourceid ? redirectsourceid : "LIBRARY",
          });

          window.dataLayer = window.dataLayer || [];
          window.dataLayer.push({
            event: "gtm.load",
            ...this.$route.query,
            itemDetails: { ...this.itemDetails },
          });
          this.reverseTimeCounter();
          setTimeout(() => {
            window.location.href = res.url;
          }, 4000);
        })
        .catch(() => {
          return;
        });
    },
    randomFeedImage(item) {
      let i = 15; // i = number of given random images
      let alternateImgUrl = require(`@/assets/images/library/blank-feed/${[
        Math.floor(Math.random() * i),
      ]}.png`);
      item.imageUrl = alternateImgUrl;
      // this.$set(this.libraryItem, item);
    },
    altSrcImage(e) {
      return (e.target.src = require(`@/assets/images/library/getboarded-logo.svg`));
    },
  },
};
</script>

<style lang="scss" scoped>
$primary-color: #101828;
.redirect {
  &__heading {
    background: #f9e7ca;
    padding: 1em 3.15em;
    font-size: 2.5rem;
    color: $primary-color;
  }

  &__description {
    padding: 1.5em 8em;

    &__content {
      width: 81%;
      .tag {
        &__text {
          padding: 0.35em 0.75em;
          background: #f2f4f7;
          border-radius: 2em;
          color: $primary-color;
        }
      }
    }

    .course {
      &__content {
        .course-img {
          margin-right: 2em;
          width: 15%;
          overflow: hidden;
          height: 12em;
        }

        .details {
          width: 85%;

          &__title {
            margin-bottom: 0.85em;

            p {
              color: #344054;
            }
          }

          &__heading {
            width: 75%;
            margin-bottom: 0.85em;

            h4 {
              color: $primary-color;
            }
          }

          &__text {
            width: 75%;
          }

          &__logo {
            margin-right: 0.75em;
            width: 1.5em;
          }
        }
      }
    }
  }

  .clip-text {
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
    text-overflow: ellipsis;
    &-3 {
      -webkit-line-clamp: 3;
    }
  }
}

@media only screen and (max-width: 1200px) {
  .redirect {
    &__description {
      .course {
        &__content {
          .course-img {
            width: 30%;
            margin-right: 1.75em;

            &__logo {
              width: 2em;
            }
          }
        }
      }
    }
  }
}

@media only screen and (max-width: 991px) {
  .redirect {
    &__heading {
      padding: 0.75em 1.75em;
      font-size: 2em;
    }

    &__description {
      padding: 0.75em 3.5em;

      &__content {
        width: 100%;
        padding: 2em 0;

        p {
          font-size: 1em;
        }
      }

      .course {
        &__content {
          .course-img {
            width: 25%;
            margin-right: 1.75em;

            &__logo {
              width: 2em;
            }
          }

          .details {
            width: 70%;

            &__heading {
              width: 100%;
            }

            &__text {
              width: 100%;
            }

            &__logo {
              width: 1.25em;
            }
          }
        }
      }
    }
  }
}

@media only screen and (max-width: 600px) {
  .redirect {

    &__heading {
      padding: 0.5em 1.5em;
      font-size: 1.5em;
    }

    &__description {
      padding: 0.5em 2.5em;

      .course {
        &__content {
          padding: 0;
          flex-direction: column;

          .course-img {
            width: 100%;

            &__logo {
              width: 1.75em;
            }
          }

          .details {
            width: 100%;

            &__logo {
              margin-right: 0.5em;
            }
          }
        }
      }
    }
  }
}
</style>
