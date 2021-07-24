<template>
  <div class="py-12">
    <Loader v-if="showLoader" />
    <News :AllNews="allNews[0]" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      allNews: [],
      showLoader: false
    };
  },
  created() {
    this.allNews = [];
    this.showLoader = true;
    fetch(
      `https://contextualwebsearch-websearch-v1.p.rapidapi.com/api/search/NewsSearchAPI?q=drugs&pageNumber=1&pageSize=10&autoCorrect=true&fromPublishedDate=null&toPublishedDate=null`,
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
        if (this.allNews[0].length === 0) alert("Try Different Keywords");
        console.log(this.allNews);
      })
      .catch(err => {
        console.error(err);
      });
  },
  mounted() {
    const image = document.querySelectorAll("img");

    image.forEach(img => {
      if (!img.complete && img.naturalHeight == 0) {
        alert("error img");
      }
    });
  }
};
</script>
