<script>
import ChooseWordsNumber from './components/ChooseWordsNumber.vue'
import TypingWindow from './components/TypingWindow.vue';
import StatsAfterTyping from './components/StatsAfterTyping.vue';
import { useStatsStore } from './stores/StatsStore';
import { mapState} from 'pinia';
export default {
	components:{
		ChooseWordsNumber,
		TypingWindow,
		StatsAfterTyping
	},
	data(){
		return{
		}
	},
	computed:{
		...mapState(useStatsStore,['typingIsOver'])
	},
};
</script>
<template>
  <main class="h-screen bg-gray-500">
    <div class="container mx-auto h-full flex flex-col justify-evenly items-center">
      <ChooseWordsNumber />
			<StatsAfterTyping v-if="typingIsOver"/>
      <TypingWindow  />
    </div>
  </main>
</template>

<style lang="scss" scoped></style>
