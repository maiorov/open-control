<template>
  <q-footer
    bordered
    style="padding-bottom: calc(env(safe-area-inset-bottom) - 16px)"
  >
    <div class="row justify-around q-pt-xs q-pb-sm">
      <!-- Home -->
      <q-btn
        flat
        no-caps
        :to="state.navItems.value.home.to"
        class="q-btn__push"
      >
        <template #default>
          <div class="column">
            <svg
              :width="svg.width"
              :height="svg.height"
              viewBox="0 0 100 100"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                :fill="
                  router.currentRoute.value.path ===
                  state.navItems.value.home.to
                    ? 'var(--q-accent)'
                    : 'var(--q-secondary)'
                "
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M58.3048 14.3078C53.5685 10.0979 46.4318 10.0979 41.6956 14.3078L9.73205 42.72C8.01209 44.2487 7.85717 46.8825 9.38601 48.6025C10.9148 50.322 13.5485 50.477 15.2684 48.9483L16.6669 47.7054V71.1083C16.6667 74.802 16.6665 77.9845 17.0091 80.5333C17.3763 83.2645 18.2045 85.8829 20.328 88.0062C22.4516 90.13 25.0698 90.9579 27.8011 91.3254C30.3497 91.6679 33.5322 91.6675 37.2259 91.6675H62.7743C66.4681 91.6675 69.6506 91.6679 72.1993 91.3254C74.9306 90.9579 77.5489 90.13 79.6722 88.0062C81.796 85.8829 82.6239 83.2645 82.9914 80.5333C83.3339 77.9845 83.3339 74.802 83.3335 71.1087V47.7054L84.7318 48.9483C86.4518 50.477 89.0856 50.322 90.6143 48.6025C92.1431 46.8825 91.9885 44.2487 90.2685 42.72L58.3048 14.3078ZM50.0002 66.6675C47.6989 66.6675 45.8335 68.5329 45.8335 70.8341V79.1675C45.8335 81.4687 43.9681 83.3341 41.6668 83.3341C39.3657 83.3341 37.5002 81.4687 37.5002 79.1675V70.8341C37.5002 63.9304 43.0964 58.3341 50.0002 58.3341C56.9039 58.3341 62.5002 63.9304 62.5002 70.8341V79.1675C62.5002 81.4687 60.6348 83.3341 58.3335 83.3341C56.0323 83.3341 54.1668 81.4687 54.1668 79.1675V70.8341C54.1668 68.5329 52.3014 66.6675 50.0002 66.6675Z"
              />
            </svg>
            <span
              style="font-size: 13px"
              :class="
                router.currentRoute.value.path === state.navItems.value.home.to
                  ? 'text-accent'
                  : 'text-secondary'
              "
            >
              {{ state.navItems.value.home.label }}
            </span>
          </div>
        </template>
      </q-btn>

      <!-- Chats -->
      <q-btn
        flat
        no-caps
        :to="state.navItems.value.chats.to"
        class="q-btn__push"
      >
        <template #default>
          <div class="column">
            <svg
              :width="svg.width"
              :height="svg.height"
              viewBox="0 0 100 100"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M29.1668 41.6673C29.1668 39.3662 31.0323 37.5007 33.3335 37.5007H33.3752C35.6763 37.5007 37.5418 39.3662 37.5418 41.6673C37.5418 43.9686 35.6763 45.834 33.3752 45.834H33.3335C31.0323 45.834 29.1668 43.9686 29.1668 41.6673ZM45.8335 41.6673C45.8335 39.3662 47.6989 37.5007 50.0002 37.5007H50.0418C52.3431 37.5007 54.2085 39.3662 54.2085 41.6673C54.2085 43.9686 52.3431 45.834 50.0418 45.834H50.0002C47.6989 45.834 45.8335 43.9686 45.8335 41.6673ZM66.6668 37.5007C64.3656 37.5007 62.5002 39.3662 62.5002 41.6673C62.5002 43.9686 64.3656 45.834 66.6668 45.834H66.7085C69.0098 45.834 70.8752 43.9686 70.8752 41.6673C70.8752 39.3662 69.0098 37.5007 66.7085 37.5007H66.6668ZM28.8925 8.33399C28.9837 8.33399 29.0751 8.33399 29.1668 8.33399H71.1077C74.8014 8.33379 77.9839 8.33362 80.5327 8.67629C83.2639 9.04349 85.8822 9.87158 88.0056 11.9952C90.1293 14.1188 90.9573 16.7369 91.3248 19.4682C91.6673 22.0168 91.6673 25.1994 91.6668 28.8932V54.4415C91.6673 58.1352 91.6673 61.3177 91.3248 63.8665C90.9573 66.5977 90.1293 69.2161 88.0056 71.3394C85.8822 73.4632 83.2639 74.2911 80.5327 74.6586C77.9839 75.0011 74.8014 75.0011 71.1077 75.0007H58.3335C57.8602 75.0007 57.3989 75.1507 57.016 75.429L38.6488 88.7869C34.7026 91.6569 29.1668 88.8382 29.1668 83.9586V75.0007C25.942 75.0007 22.6718 75.0894 19.4677 74.6586C16.7364 74.2911 14.1183 73.4632 11.9947 71.3394C9.87109 69.2161 9.04301 66.5977 8.6758 63.8665C8.33313 61.3177 8.3333 58.1352 8.33351 54.4415V29.1673C8.33351 29.0756 8.33351 28.9842 8.33351 28.893C8.3333 25.1994 8.33313 22.0168 8.6758 19.4682C9.04301 16.7369 9.87109 14.1188 11.9947 11.9952C14.1183 9.87158 16.7364 9.04349 19.4677 8.67629C22.0163 8.33362 25.1989 8.33379 28.8925 8.33399Z"
                :fill="
                  router.currentRoute.value.path ===
                  state.navItems.value.chats.to
                    ? 'var(--q-accent)'
                    : 'var(--q-secondary)'
                "
              />
            </svg>

            <span
              style="font-size: 13px"
              :class="
                router.currentRoute.value.path === state.navItems.value.chats.to
                  ? 'text-accent'
                  : 'text-secondary'
              "
            >
              {{ state.navItems.value.chats.label }}
            </span>
          </div>
        </template>
      </q-btn>

      <!-- CHAT BOT -->
      <q-btn
        v-if="!user.roles.includes('inspector')"
        round
        flat
        class="q-btn__search q-btn__push shadow-3"
        :to="router.currentRoute.value.path + ROUTE_PATHS.CHAT_BOT"
      >
        <template #default>
          <div class="bg-banner">
            <!-- * new -->
            <svg
              class="absolute-center"
              :width="75 / 1.75"
              :height="75 / 1.75"
              viewBox="0 0 100 100"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M62.5 62.5L87.5 87.5M41.6667 70.8333C25.5584 70.8333 12.5 57.775 12.5 41.6667C12.5 25.5584 25.5584 12.5 41.6667 12.5C57.775 12.5 70.8333 25.5584 70.8333 41.6667C70.8333 57.775 57.775 70.8333 41.6667 70.8333Z"
                stroke="white"
                stroke-width="8"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>

            <!-- * original -->
            <!--            <svg-->
            <!--              class="absolute-center"-->
            <!--              width="44"-->
            <!--              height="44"-->
            <!--              viewBox="0 0 18 18"-->
            <!--              fill="none"-->
            <!--              xmlns="http://www.w3.org/2000/svg"-->
            <!--            >-->
            <!--              <path-->
            <!--                d="M6.51562 0C7.67188 0 8.75 0.296875 9.75 0.890625C10.75 1.45312 11.5312 2.23438 12.0938 3.23438C12.6875 4.23437 12.9844 5.32812 12.9844 6.51562C12.9844 8.10938 12.4688 9.51562 11.4375 10.7344L11.7188 11.0156H12.5156L17.4844 15.9844L15.9844 17.4844L11.0156 12.5156V11.7188L10.7344 11.4375C9.51562 12.4688 8.10938 12.9844 6.51562 12.9844C5.32812 12.9844 4.23438 12.7031 3.23438 12.1406C2.23438 11.5469 1.4375 10.75 0.84375 9.75C0.28125 8.75 0 7.67188 0 6.51562C0 5.32812 0.28125 4.23437 0.84375 3.23438C1.4375 2.23438 2.23438 1.45312 3.23438 0.890625C4.23438 0.296875 5.32812 0 6.51562 0ZM6.51562 2.01562C5.26562 2.01562 4.20312 2.45312 3.32812 3.32812C2.45312 4.20313 2.01562 5.26562 2.01562 6.51562C2.01562 7.76562 2.45312 8.82812 3.32812 9.70312C4.20312 10.5781 5.26562 11.0156 6.51562 11.0156C7.76562 11.0156 8.82812 10.5781 9.70312 9.70312C10.5781 8.82812 11.0156 7.76562 11.0156 6.51562C11.0156 5.26562 10.5781 4.20313 9.70312 3.32812C8.82812 2.45312 7.76562 2.01562 6.51562 2.01562Z"-->
            <!--                fill="var(&#45;&#45;q-accent)"-->
            <!--              />-->
            <!--            </svg>-->
          </div>
        </template>
      </q-btn>

      <!-- Meetings -->
      <q-btn
        flat
        no-caps
        :to="state.navItems.value.meetings.to"
        class="q-btn__push"
      >
        <template #default>
          <div class="column">
            <svg
              :width="svg.width"
              :height="svg.height"
              viewBox="0 0 100 100"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M20.8335 12.5007V18.1135C18.1291 18.9187 15.735 20.1698 13.7855 22.1193C11.4255 24.4793 10.089 27.4908 9.32791 30.9156C8.57733 34.2931 8.3335 38.3155 8.3335 42.9673V65.3673C8.3335 70.019 8.57733 74.0415 9.32791 77.419C10.089 80.844 11.4255 83.8552 13.7855 86.2152C16.1455 88.5752 19.157 89.9119 22.5818 90.6727C25.9592 91.4236 29.9817 91.6673 34.6335 91.6673H65.3668C70.0185 91.6673 74.041 91.4236 77.4185 90.6727C80.8435 89.9119 83.8547 88.5752 86.2147 86.2152C88.5747 83.8552 89.9114 80.844 90.6722 77.419C91.4231 74.0415 91.6668 70.019 91.6668 65.3673V42.9673C91.6668 38.3155 91.4231 34.2931 90.6722 30.9156C89.9114 27.4908 88.5747 24.4793 86.2147 22.1193C84.2652 20.1698 81.8714 18.9187 79.1668 18.1135V12.5007C79.1668 10.1995 77.3014 8.33398 75.0002 8.33398C72.6989 8.33398 70.8335 10.1995 70.8335 12.5007V16.8122C69.1206 16.7093 67.2981 16.6673 65.3668 16.6673H34.6335C32.7025 16.6673 30.8799 16.7093 29.1668 16.8122V12.5007C29.1668 10.1995 27.3013 8.33398 25.0002 8.33398C22.699 8.33398 20.8335 10.1995 20.8335 12.5007ZM25.0002 37.5007C25.0002 35.1995 26.8657 33.334 29.1668 33.334H70.8335C73.1347 33.334 75.0002 35.1995 75.0002 37.5007C75.0002 39.8018 73.1347 41.6673 70.8335 41.6673H29.1668C26.8657 41.6673 25.0002 39.8018 25.0002 37.5007Z"
                :fill="
                  router.currentRoute.value.path ===
                  state.navItems.value.meetings.to
                    ? 'var(--q-accent)'
                    : 'var(--q-secondary)'
                "
              />
            </svg>

            <span
              style="font-size: 13px"
              :class="
                router.currentRoute.value.path ===
                state.navItems.value.meetings.to
                  ? 'text-accent'
                  : 'text-secondary'
              "
            >
              {{ state.navItems.value.meetings.label }}
            </span>
          </div>
        </template>
      </q-btn>

      <!-- Profile -->
      <q-btn
        flat
        no-caps
        :to="state.navItems.value.profile.to"
        class="q-btn__push"
      >
        <template #default>
          <div class="column">
            <svg
              :width="svg.width"
              :height="svg.height"
              viewBox="0 0 100 100"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M25 33.334C25 19.5269 36.1929 8.33398 50 8.33398C63.8071 8.33398 75 19.5269 75 33.334C75 47.1411 63.8071 58.334 50 58.334C36.1929 58.334 25 47.1411 25 33.334Z"
                :fill="
                  router.currentRoute.value.path ===
                  state.navItems.value.profile.to
                    ? 'var(--q-accent)'
                    : 'var(--q-secondary)'
                "
              />
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M22.6289 70.4284C29.3994 67.5901 38.4304 66.668 50 66.668C61.5458 66.668 70.5629 67.5863 77.3275 70.4101C84.5883 73.4409 89.045 78.5901 91.4208 86.0792C92.3033 88.8626 90.2158 91.668 87.33 91.668H12.6441C9.77007 91.668 7.69494 88.875 8.5704 86.1071C10.939 78.6184 15.3799 73.4671 22.6289 70.4284Z"
                :fill="
                  router.currentRoute.value.path ===
                  state.navItems.value.profile.to
                    ? 'var(--q-accent)'
                    : 'var(--q-secondary)'
                "
              />
            </svg>

            <span
              style="font-size: 13px"
              :class="
                router.currentRoute.value.path ===
                state.navItems.value.profile.to
                  ? 'text-accent'
                  : 'text-secondary'
              "
            >
              {{ state.navItems.value.profile.label }}
            </span>
          </div>
        </template>
      </q-btn>
    </div>
  </q-footer>
</template>

<script setup>
import { ROUTE_PATHS } from 'src/constants/paths';
import { useRouter } from 'vue-router';
import { storeToRefs } from 'pinia';
import { useIndexStore } from 'stores/store-index';
import { useAuthStore } from 'stores/store-auth';
const router = useRouter();

const state = storeToRefs(useIndexStore());

const svg = {
  width: 33,
  height: 33,
};

const { user } = storeToRefs(useAuthStore());
</script>

<style scoped lang="scss">
::v-deep(.q-btn) {
  width: 60px;
  height: 60px;
}

.q-btn__search {
  width: 75px;
  height: 75px;
  margin-top: -30px;
}
.q-btn__search div {
  width: 100%;
  height: 100%;
  border-radius: 100%;
  position: relative;
}
</style>

<style scoped>
svg {
  margin: 0 auto;
  transition: 0.275s;
}

svg path,
span,
div {
  transition: 0.275s;
}
</style>
