<template>
  <div>
    <div class="flex flex-col sm:flex-row">
      <input
        type="text"
        v-model="text"
        class="mb-4 sm:mb-0 border border-gray-400 focus:border-gray-700 rounded text-sm sm:text-xl w-full mr-4  p-2"
      />
      <button
        class="text-sm sm:text-xl py-2 px-6 bg-gray-800 hover:bg-gray-900 text-white rounded"
        @click="searchNews"
      >
        Search
      </button>
    </div>
    <div class="py-12">
      <Loader v-if="showLoader" />
      <News :AllNews="allNews[0]" />
      <div class="text-center text-xl font-black">
        {{ errorMsg }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: "",
      allNews: [],
      showLoader: false,
      errorMsg: ""
    };
  },
  methods: {
    searchNews() {
      this.allNews = [];
      this.showLoader = true;
      fetch(
        `https://contextualwebsearch-websearch-v1.p.rapidapi.com/api/search/NewsSearchAPI?q=${this.text}&pageNumber=1&pageSize=10&autoCorrect=true&fromPublishedDate=null&toPublishedDate=null`,
        {
          method: "GET",
          headers: {
            "x-rapidapi-key":
              "42e66501ccmshbda94d50b8eb9d9p16bd9cjsn7f7601e2b6fa",
            "x-rapidapi-host": "contextualwebsearch-websearch-v1.p.rapidapi.com"
          }
        }
      )
        .then(res => res.json())
        .then(data => {
          this.showLoader = false;
          this.allNews.push(data.value);
          if (this.allNews[0].length === 0) {
            this.errorMsg = "Try Different Keywords.";
          }
          console.log(this.allNews);
        })
        .catch(err => {
          console.error(err);
        });
      this.text = "";
    }
  }
};
</script>
