<script lang="ts" setup>
import { Icon } from '@iconify/vue';
import {
  useDashboard,
  LoadingStatus,
  type ChainConfig,
} from '@/stores/useDashboard';
import ChainSummary from '@/components/ChainSummary.vue';
import AdBanner from '@/components/ad/AdBanner.vue';

import { computed, onMounted, ref } from 'vue';
import { useBlockchain } from '@/stores';

const dashboard = useDashboard();

const keywords = ref('');
const chains = computed(() => {
  if (keywords.value) {
    const lowercaseKeywords = keywords.value.toLowerCase();

    return Object.values(dashboard.chains).filter(
      (x: ChainConfig) => x.chainName.toLowerCase().indexOf(lowercaseKeywords) > -1
      || x.prettyName.toLowerCase().indexOf(lowercaseKeywords) > -1
    );
  } else {
    return Object.values(dashboard.chains);
  }
});

const featured = computed(() => {
  const names = ["cosmos", "osmosis", "akash", "celestia", "evmos", "injective", "dydx", "noble"];
  return chains.value
    .filter(x => names.includes(x.chainName))
    .sort((a, b)=> (names.indexOf(a.chainName) - names.indexOf(b.chainName)))
})

const chainStore = useBlockchain()

</script>
<template>
  <div class="">
    <div class="flex md:!flex-row flex-col items-center justify-center mb-6 mt-14 gap-2">
      <div class="w-16 rounded-full">
      <svg version="1.1" id="Слой_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 viewBox="0 0 904 397" style="enable-background:new 0 0 904 397;" xml:space="preserve">
<!-- TODO: this main page svg image -->
<g :fill="chainStore.current?.themeColor||'#666CFF'" class=" dark:invert" stroke="none">
	<path class="st0" d="M83.5,351.1c-8.1-7.8-12.1-19.2-12.1-34.3v-76c0-9.6-1.7-16.2-5-19.7c-3.4-3.4-9.8-5.2-19.4-5.2v-37.2
		c9.5,0,16-1.7,19.4-5.2s5-10,5-19.7V77.8c0-15.1,4-26.6,12.1-34.3c8-7.8,18.3-11.5,31-11.5h21.7v37.2H130c-7,0-12.2,2.1-15.5,6.4
		c-3.4,4.3-5,11.9-5,23v62c0,19.3-7.9,31.4-23.7,36.4v0.8c15.8,4.9,23.7,17.1,23.7,36.4v62c0,11,1.7,18.7,5,23
		c3.4,4.3,8.5,6.4,15.5,6.4h6.2v37.3h-21.7C101.8,362.7,91.5,358.8,83.5,351.1z"/>
	<path class="st0" d="M198.6,52.6h57.7L300.5,342h-42.7l-7.8-57.5v0.8h-48.4l-7.8,56.6h-39.5L198.6,52.6z M245.1,246.1l-18.9-143
		h-0.8l-18.6,143H245.1z"/>
	<path class="st0" d="M314.1,301.5L393.1,94H318V52.6h121v40.6l-79.1,207.6h79.1v41.4H314.1V301.5z"/>
	<path class="st0" d="M462.9,52.6h42.7v121.9l54.3-121.9h42.7l-50.8,106.3L603.3,342h-44.6l-36-129l-17.1,36.8v92.2h-42.7V52.6
		L462.9,52.6z"/>
	<path class="st0" d="M623.4,52.6h63.2c22,0,38,5.5,48.1,16.4s15.1,27.6,15.1,50.2V137c0,30-9.3,49.1-27.9,57v0.8
		c10.3,3.3,17.7,10,21.9,20.2c4.3,10.2,6.4,23.9,6.4,41v50.9c0,8.3,0.3,15,0.8,20.1s1.8,10.2,3.9,15.1h-43.4
		c-1.5-4.7-2.6-9.1-3.1-13.3c-0.5-4.1-0.8-11.5-0.8-22.3v-52.9c0-13.3-2-22.5-6-27.7c-4-5.2-10.9-7.9-20.7-7.9h-14.7V342h-42.7
		L623.4,52.6L623.4,52.6z M681.5,176.7c8.5,0,15-2.3,19.2-7c4.3-4.7,6.4-12.6,6.4-23.6v-22.3c0-10.4-1.7-18.1-5.3-22.8
		c-3.5-4.7-9-7-16.4-7H666v82.7H681.5L681.5,176.7z"/>
	<path class="st0" d="M773.4,325.5h6.2c7,0,12.2-2.1,15.5-6.4c3.4-4.3,5-11.9,5-23v-62c0-19.2,7.9-31.4,23.7-36.4V197
		c-15.8-4.9-23.7-17.1-23.7-36.4V98.5c0-11-1.7-18.7-5-23c-3.4-4.3-8.5-6.4-15.5-6.4h-6.2V31.9h21.7c12.6,0,23,3.8,31,11.5
		c8,7.8,12.1,19.2,12.1,34.3v76c0,9.6,1.7,16.2,5,19.7c3.4,3.4,9.8,5.2,19.4,5.2v37.2c-9.5,0-16,1.7-19.4,5.2c-3.4,3.4-5,10-5,19.7
		v76c0,15.1-4,26.6-12.1,34.3c-8,7.7-18.4,11.5-31,11.5h-21.7V325.5z"/>
</g>
</svg>
        <!-- <svg version="1.0" xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 150.000000 132.000000"
          preserveAspectRatio="xMidYMid meet">
          <g transform="translate(0.000000,132.000000) scale(0.100000,-0.100000)"
          :fill="chainStore.current?.themeColor||'#666CFF'" class=" dark:invert" stroke="none">
            <path d="M500 1310 l-125 -5 -182 -315 c-100 -173 -182 -321 -182 -329 -1 -7
            81 -159 181 -337 l183 -324 372 0 371 0 186 325 c102 179 186 330 186 337 0 7
            -82 157 -182 335 l-183 323 -250 -2 c-137 -1 -306 -5 -375 -8z m588 -454 c61
            -106 112 -197 112 -201 0 -4 -50 -95 -111 -201 l-112 -194 -231 0 -231 0 -105
            181 c-58 100 -109 190 -114 200 -6 14 17 63 104 213 l112 196 232 0 231 0 113
            -194z"/>
            <path d="M591 1001 l-54 -6 -87 -150 -88 -150 176 -3 c97 -1 181 -1 187 2 9 3
            165 267 183 308 4 9 -233 7 -317 -1z"/>
            <path d="M872 824 l-90 -159 36 -66 c113 -201 147 -258 153 -251 8 8 179 302
            179 307 0 2 -37 68 -83 147 -46 78 -88 151 -94 162 -9 16 -24 -5 -101 -140z"/>
            <path d="M360 625 c0 -7 148 -263 172 -297 l19 -28 186 0 c101 0 183 3 181 8
            -1 4 -43 78 -93 165 l-90 157 -187 0 c-104 0 -188 -2 -188 -5z"/>
          </g>
        </svg> -->
      </div>
      <h1 class="text-primary dark:invert text-3xl md:!text-6xl font-bold">
        {{ $t('pages.title') }}
      </h1>
    </div>
    <div class="text-center text-base">
      <p class="mb-1">
        {{ $t('pages.slogan') }}
      </p>
    </div>
    <div
      v-if="dashboard.status !== LoadingStatus.Loaded"
      class="flex justify-center"
    >
      <progress class="progress progress-info w-80 h-1"></progress>
    </div>

    <div v-if="featured.length>0" class="text-center text-base mt-6 text-primary">
      <h2 class="mb-6"> Featured Blockchains 🔥 </h2>
    </div>

    <div v-if="featured.length>0"
      class="grid grid-cols-1 gap-4 mt-6 md:!grid-cols-3 lg:!grid-cols-4 2xl:!grid-cols-5"
    >
    <ChainSummary
        v-for="(chain, index) in featured"
        :key="index"
        :name="chain.chainName"
      />
    </div>

    <AdBanner id="home-banner-ad" unit="banner" width="970px" height="90px" />

    <div class="text-center text-base mt-6 text-primary">
      <h2 class="mb-6">{{ $t('pages.description') }}</h2>
    </div>

    <div class="flex items-center rounded-lg bg-base-100  border border-gray-200 dark:border-gray-700 mt-10">
      <Icon icon="mdi:magnify" class="text-2xl text-gray-400 ml-3"/>
      <input :placeholder="$t('pages.search_placeholder')" class="px-4 h-10 bg-transparent flex-1 outline-none text-base" v-model="keywords" />
      <div class="px-4 text-base hidden md:!block">{{ chains.length }}/{{ dashboard.length }}</div>
    </div>

    <div
      class="grid grid-cols-1 gap-4 mt-6 md:!grid-cols-3 lg:!grid-cols-4 2xl:!grid-cols-5"
    >
      <ChainSummary
        v-for="(chain, index) in chains"
        :key="index"
        :name="chain.chainName"
      />
    </div>
  </div>
</template>

<style scoped>
 .logo path{
  fill: #171d30;
}
</style>@/components/ad/ad
