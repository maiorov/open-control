<template>
  <div>
    <div class="text-h4">Действия</div>

    <div class="row no-wrap q-gutter-md service_cards__wrapper">
      <q-intersection
        v-for="service in services"
        :key="service.name"
        transition="scale"
        once
      >
        <q-card
          flat
          v-ripple
          class="q-hoverable service_card bg-banner"
          :class="service.disabled ? 'q-btn__disabled' : 'q-btn__push'"
          @click="
            service.disabled
              ? (isSubscriptionOfferShown = true)
              : service === services.meetings
              ? router.push(ROUTE_PATHS.HOME + ROUTE_PATHS.CHAT_BOT)
              : service === services.complaint
              ? (isComplaintModalShown = true)
              : ''
          "
        >
          <q-card-section class="column">
            <div style="margin: 0 auto">
              <svg
                v-if="service === services.calculator"
                width="48"
                height="48"
                viewBox="0 0 160 160"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <g clip-path="url(#clip0_29_1751)">
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M53.3334
              46.6673C53.3334 42.9855 56.3182 40.0007 60.0001
              40.0007H100C103.682 40.0007 106.667 42.9855 106.667
              46.6673C106.667 50.3492 103.682 53.334 100 53.334H60.0001C56.3182
              53.334 53.3334 50.3492 53.3334 46.6673ZM100 86.6673C103.682
              86.6673 106.667 89.652 106.667 93.334V113.334C106.667 117.016
              103.682 120.001 100 120.001C96.3181 120.001 93.3334 117.016
              93.3334 113.334V93.334C93.3334 89.652 96.3181 86.6673 100
              86.6673ZM100 66.6673C96.3181 66.6673 93.3334 69.652 93.3334
              73.334C93.3334 77.016 96.3181 80.0007 100 80.0007H100.067C103.749
              80.0007 106.733 77.016 106.733 73.334C106.733 69.652 103.749
              66.6673 100.067 66.6673H100ZM73.3334 73.334C73.3334 69.652 76.3181
              66.6673 80.0001 66.6673H80.0668C83.7488 66.6673 86.7334 69.652
              86.7334 73.334C86.7334 77.016 83.7488 80.0007 80.0668
              80.0007H80.0001C76.3181 80.0007 73.3334 77.016 73.3334
              73.334ZM60.0001 66.6673C56.3182 66.6673 53.3334 69.652 53.3334
              73.334C53.3334 77.016 56.3182 80.0007 60.0001
              80.0007H60.0668C63.7486 80.0007 66.7334 77.016 66.7334
              73.334C66.7334 69.652 63.7486 66.6673 60.0668
              66.6673H60.0001ZM53.3334 93.334C53.3334 89.652 56.3182 86.6673
              60.0001 86.6673H60.0668C63.7486 86.6673 66.7334 89.652 66.7334
              93.334C66.7334 97.016 63.7486 100.001 60.0668
              100.001H60.0001C56.3182 100.001 53.3334 97.016 53.3334
              93.334ZM80.0001 86.6673C76.3181 86.6673 73.3334 89.652 73.3334
              93.334C73.3334 97.016 76.3181 100.001 80.0001
              100.001H80.0668C83.7488 100.001 86.7334 97.016 86.7334
              93.334C86.7334 89.652 83.7488 86.6673 80.0668
              86.6673H80.0001ZM73.3334 113.334C73.3334 109.652 76.3181 106.667
              80.0001 106.667H80.0668C83.7488 106.667 86.7334 109.652 86.7334
              113.334C86.7334 117.016 83.7488 120.001 80.0668
              120.001H80.0001C76.3181 120.001 73.3334 117.016 73.3334
              113.334ZM60.0001 106.667C56.3182 106.667 53.3334 109.652 53.3334
              113.334C53.3334 117.016 56.3182 120.001 60.0001
              120.001H60.0668C63.7486 120.001 66.7334 117.016 66.7334
              113.334C66.7334 109.652 63.7486 106.667 60.0668
              106.667H60.0001ZM59.5612 13.334C59.707 13.334 59.8534 13.334
              60.0001 13.334H100.439C106.349 13.3337 111.441 13.3334 115.519
              13.8817C119.889 14.4692 124.078 15.7941 127.475 19.1919C130.873
              22.5897 132.198 26.7787 132.786 31.1487C133.334 35.2265 133.334
              40.3186 133.333 46.2285V113.773C133.334 119.683 133.334 124.775
              132.786 128.853C132.198 133.223 130.873 137.412 127.475
              140.809C124.078 144.207 119.889 145.532 115.519 146.12C111.441
              146.668 106.349 146.668 100.439 146.667H59.5614C53.6514 146.668
              48.5593 146.668 44.4815 146.12C40.1114 145.532 35.9224 144.207
              32.5246 140.809C29.1269 137.412 27.802 133.223 27.2144
              128.853C26.6662 124.775 26.6664 119.683 26.6668
              113.773V46.6673C26.6668 46.5206 26.6668 46.3743 26.6668
              46.2285C26.6664 40.3186 26.6662 35.2265 27.2144 31.1487C27.802
              26.7787 29.1269 22.5897 32.5246 19.1919C35.9224 15.7941 40.1114
              14.4692 44.4815 13.8817C48.5592 13.3334 53.6514 13.3337 59.5612
              13.334Z"
                    fill="white"
                  />
                </g>
                <defs>
                  <clipPath id="clip0_29_1751">
                    <rect width="160" height="160" fill="white" />
                  </clipPath>
                </defs>
              </svg>

              <svg
                v-if="service === services.meetings"
                width="48"
                height="48"
                viewBox="0 0 160 160"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M33.3333 20.0007V28.9812C29.0063 30.2696 25.1757 32.2713 22.0565 35.3905C18.2805 39.1665 16.1421 43.9849 14.9243 49.4646C13.7234 54.8685 13.3333 61.3045 13.3333 68.7473V104.587C13.3333 112.03 13.7234 118.466 14.9243 123.87C16.1421 129.35 18.2805 134.168 22.0565 137.944C25.8325 141.72 30.6509 143.859 36.1305 145.076C41.5345 146.277 47.9704 146.667 55.4133 146.667H104.587C112.029 146.667 118.465 146.277 123.869 145.076C129.349 143.859 134.167 141.72 137.943 137.944C141.719 134.168 143.858 129.35 145.075 123.87C146.277 118.466 146.667 112.03 146.667 104.587V68.7473C146.667 61.3045 146.277 54.8685 145.075 49.4646C143.858 43.9849 141.719 39.1665 137.943 35.3905C134.824 32.2713 130.994 30.2696 126.667 28.9812V20.0007C126.667 16.3188 123.682 13.334 120 13.334C116.318 13.334 113.333 16.3188 113.333 20.0007V26.8991C110.593 26.7345 107.677 26.6673 104.587 26.6673H55.4133C52.3236 26.6673 49.4075 26.7345 46.6666 26.8991V20.0007C46.6666 16.3188 43.6818 13.334 39.9999 13.334C36.3181 13.334 33.3333 16.3188 33.3333 20.0007ZM39.9999 60.0006C39.9999 56.3188 42.9847 53.334 46.6666 53.334H113.333C117.015 53.334 120 56.3188 120 60.0006C120 63.6825 117.015 66.6673 113.333 66.6673H46.6666C42.9847 66.6673 39.9999 63.6825 39.9999 60.0006Z"
                  fill="white"
                />
              </svg>

              <template v-if="service === services.complaint">
                <transition
                  appear
                  enter-active-class="animated zoomIn"
                  leave-active-class="anime iodajsoi dja"
                >
                  <svg
                    v-if="!isCompaintSent"
                    width="48"
                    height="48"
                    viewBox="0 0 160 160"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M73.3698 86.6789C73.3698 90.3609 76.3545 93.3455 80.0365 93.3455C83.7185 93.3455 86.7031 90.3609 86.7031 86.6789V66.6789C86.7031 62.997 83.7185 60.0122 80.0365 60.0122C76.3545 60.0122 73.3698 62.997 73.3698 66.6789V86.6789ZM86.7031 106.604C86.7031 102.922 83.7185 99.9375 80.0365 99.9375C76.3545 99.9375 73.3698 102.922 73.3698 106.604V106.679C73.3698 110.361 76.3545 113.346 80.0365 113.346C83.7185 113.346 86.7031 110.361 86.7031 106.679V106.604ZM62.5521 31.0879C70.1725 17.3717 89.8985 17.3717 97.5185 31.0879L141.525 110.3C148.93 123.63 139.291 140.012 124.042 140.012H36.0288C20.7791 140.012 11.1397 123.63 18.5456 110.3L62.5521 31.0879Z"
                      fill="white"
                    />
                  </svg>
                </transition>

                <svg
                  v-if="isCompaintSent"
                  width="48"
                  height="48"
                  class="checkmark"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 52 52"
                >
                  <circle
                    class="checkmark__circle"
                    cx="26"
                    cy="26"
                    r="25"
                    fill="none"
                  />
                  <path
                    class="checkmark__check"
                    fill="none"
                    d="M14.1 27.2l7.1 7.2 16.7-16.8"
                  />
                </svg>
              </template>

              <svg
                v-if="service === services.consultation"
                width="48"
                height="48"
                viewBox="0 0 160 160"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <g clip-path="url(#clip0_29_1810)">
                  <path
                    d="M154.167 83.3333L127.5 19C112.645 13.1055 96.8156 10.0526 80.8338 10C64.8521 10.0526 49.0223 13.1055 34.1672 19L7.50049 83.3333V90C7.50049 97.0724 10.31 103.855 15.311 108.856C20.3119 113.857 27.0947 116.667 34.1672 116.667C41.2396 116.667 48.0224 113.857 53.0233 108.856C58.0243 103.855 60.8338 97.0724 60.8338 90V83.3333L39.5005 33.3333L40.5005 30.6667C51.3056 26.6494 62.6562 24.2894 74.1672 23.6667V136.667H50.8338C49.0657 136.667 47.37 137.369 46.1198 138.619C44.8695 139.87 44.1672 141.565 44.1672 143.333C44.1672 145.101 44.8695 146.797 46.1198 148.047C47.37 149.298 49.0657 150 50.8338 150H110.834C112.602 150 114.298 149.298 115.548 148.047C116.798 146.797 117.5 145.101 117.5 143.333C117.5 141.565 116.798 139.87 115.548 138.619C114.298 137.369 112.602 136.667 110.834 136.667H87.5005V23.6667C99.0114 24.2894 110.362 26.6494 121.167 30.6667L122.167 33.3333L100.834 83.3333V90C100.834 97.0724 103.643 103.855 108.644 108.856C113.645 113.857 120.428 116.667 127.5 116.667C134.573 116.667 141.356 113.857 146.357 108.856C151.358 103.855 154.167 97.0724 154.167 90V83.3333ZM48.1672 83.3333H18.1672L34.1672 47.6667L48.1672 83.3333ZM127.5 47.6667L141.501 83.3333H111.5L127.5 47.6667Z"
                    fill="white"
                  />
                </g>
                <defs>
                  <clipPath id="clip0_29_1810">
                    <rect width="160" height="160" fill="white" />
                  </clipPath>
                </defs>
              </svg>
            </div>

            <div class="service_card__label">
              {{ service.label }}
            </div>
          </q-card-section>
        </q-card>
      </q-intersection>
    </div>

    <SubscriptionOfferModal
      :is-shown="isSubscriptionOfferShown"
      @hide="isSubscriptionOfferShown = false"
    />
    <ComplaintModal
      :is-shown="isComplaintModalShown"
      @hide="isComplaintModalShown = false"
      @send="handleComplaintSend()"
    />
  </div>
</template>

<script setup>
import SubscriptionOfferModal from 'components/SubscriptionOfferModal.vue';
import { ref } from 'vue';
import { ROUTE_PATHS } from 'src/constants/paths';
import { useRouter } from 'vue-router';
import ComplaintModal from 'components/ComplaintModal.vue';

const router = useRouter();

const handleComplaintSend = () => {
  isComplaintModalShown.value = false;
  isCompaintSent.value = true;

  setTimeout(() => {
    isCompaintSent.value = false;
  }, 5000);
};

const services = {
  meetings: {
    value: 'meetings',
    label: 'Назначить встречу',
  },
  complaint: {
    value: 'complaint',
    label: 'Написать жалобу',
  },
  calculator: {
    value: 'calculator',
    label: 'Калькулятор рисков',
    disabled: true,
  },
  consultation: {
    value: 'consultation',
    label: 'Консультация с юрисом',
    disabled: true,
  },
};

const isSubscriptionOfferShown = ref(false);

const isComplaintModalShown = ref(false);
const isCompaintSent = ref(false);
</script>

<style scoped>
.service_cards__wrapper {
  overflow-x: scroll;
  margin-left: -24px;
  margin-right: -24px;
  padding: 0 24px 0 8px;
}

.service_cards__wrapper::-webkit-scrollbar {
  display: none;
}

.service_cards__wrapper .service_card {
  border-radius: 20px;
  color: white;
  min-width: 120px;
}

.service_card__label {
  text-align: center;
  line-height: 16px;
  font-weight: 500;
}

/*
 * check mark animation
 */
.checkmark__circle {
  stroke-dasharray: 166;
  stroke-dashoffset: 166;
  stroke-width: 2;
  stroke-miterlimit: 10;
  stroke: white;
  fill: none;
  animation: stroke 0.6s cubic-bezier(0.65, 0, 0.45, 1) forwards;
}

.checkmark {
  border-radius: 50%;
  width: 44px;
  height: 44px;
  display: block;
  stroke-width: 2;
  stroke: var(--q-accent);
  stroke-miterlimit: 10;
  margin-bottom: 9px;
  box-shadow: inset 0 0 0 white;
  animation: fill 0.4s ease-in-out 0.4s forwards,
    scale 0.3s ease-in-out 0.9s both;
}

.checkmark__check {
  transform-origin: 50% 50%;
  stroke-dasharray: 48;
  stroke-dashoffset: 48;
  animation: stroke 0.3s cubic-bezier(0.65, 0, 0.45, 1) 0.8s forwards;
}

@keyframes stroke {
  100% {
    stroke-dashoffset: 0;
  }
}
@keyframes scale {
  0%,
  100% {
    transform: none;
  }
  50% {
    transform: scale3d(1.1, 1.1, 1);
  }
}
@keyframes fill {
  100% {
    box-shadow: inset 0 0 0 30px white;
  }
}
</style>
