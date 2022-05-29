<template>
  <div class="g-lg-flow-sm p-reviw-graph-area-row-sm">
    <span style="display: flex">
      <div class="g-score p-reviw-graph-area-score">
        <star-rating
          class="star"
          :starSize="20"
          :rating="rating.rating"
          :read-only="true"
          :increment="0.01"
          :showRating="false"
        ></star-rating>
      </div>
      <div class="a-meter g-mater-visble" id="js-mater5" style="width: 150px">
        <div
          class="a-meter-bar"
          :style="{ width: rating.percentage + '%' }"
        ></div>
      </div>
      <div class="g-link g-link-visble">
        <a id="js-rate5" :data-rate="rating.rating" :title="title" @click="clickRating(rating.rating)"
          >{{ rating.ratingCount }}人</a
        >
      </div></span
    >
  </div>
</template>

<script>
import { mapMutations } from 'vuex'
import StarRating from "vue-star-rating";

export default {
  components: {
    StarRating,
  },
  props: {
    rating: {
      rating: Number,
      percentage: Number,
      ratingCount: Number,
    },
  },
  methods:{
    async clickRating(rating){
      if(this.$store.getters.getReviewList.length === 0 && this.$store.getters.getReview.reviewCount > 3){
        await this.$store.dispatch('setReview',{ goodsId: this.$route.params.goodsId, offset: 3 });
      }
       this.filterReviews(rating);

    },
    ...mapMutations([
      'filterReviews', 
    ]),
  },
  data() {
    return {
      title:
        "レビューの" +
        this.rating.percentage +
        "%に星" +
        this.rating.rating +
        "つが付いています。",
    };
  },
};
</script>

<style scoped>
#js-rate5 {
  text-decoration: underline;
  cursor: pointer;
}
#js-rate5:hover {
  text-decoration: none;
}

.p-reviw-graph-area-row-sm {
  display: flex;
  flex-wrap: wrap;
}
.a-meter .a-meter-bar {
  /* -webkit-transition: width .5s ease; */
  /* transition: width .5s ease; */
  /* float: left; */
  /* font-size: 0; */
  height: 100%;
  /* width: 0; */
}

.a-meter .a-meter-bar {
  border-radius: 4px;
  box-shadow: inset -2px 0 0 -1px #a4433c, inset 0 0 0 1px #8d3a34;
  background-color: #eb6157;
  border-top-right-radius: 0;
  border-bottom-right-radius: 0;
}
.a-meter {
  border-radius: 4px;
  overflow: hidden;
  box-shadow: inset 0 0 0 1px #e3e6e6;
  background-color: #dbdbdb;
  height: 10px;
  width: calc(100% - 110px - 4em);
  margin-left: 0px;
  margin-top: 5px;
  margin-right: 5px;
  cursor: pointer;
}
a.g-link g-link-visble {
  cursor: pointer;
}
</style>
