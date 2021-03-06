<style lang="scss" scoped>
#page-dataset {
  .figure {
    margin: auto;
  }
}
</style>

<template lang="pug">
#page-dataset
  section.section#display-section: .container.content
    .section
      h1.title.has-text-centered
        | The 1st Large-scale Video Object Segmentation Challenge
      h2.subtitle.has-text-centered.has-text-grey-light
        | Workshop in conjunction with ECCV2018, Munich, Germany

    .section
      h1.title.is-4 Introduction
      p Video object segmentation has been studied extensively in the past decade due to its importance in understanding video spatial-temporal structures as well as its value in industrial applications. Recently, data-driven algorithms (e.g. deep learning) have become the dominant approach to computer vision problems and one of the most important keys to their successes is the availability of large-scale datasets. Unfortunately, there does not exist a large-scale dataset for video object segmentation. As a result, recent algorithms for video object segmentation have to train their models on image datasets which do not contain any temporal information or video-specific characteristics, and thus would settle for suboptimal solutions. Besides, previous benchmark does not differentiate the object categories used in training and testing, and therefore cannot evaluate the true generalization ability of algorithms on unseen categories.

      p In this workshop in conjunction with a competition, we will present the first large-scale dataset for video object segmentation, which would allow participant teams to try novel and bold ideas that could not succeed with previous small-scale datasets. In contrast to previous video-object-segmentation datasets, our dataset has the following advantages:

      li Our dataset contains 4000+ high-resolution videos clips, which are downloaded from YouTube and contain diverse contents. It is more than 30 times larger than the existing largest dataset (i.e. DAVIS) for video object segmentation.

      li Our dataset consists of a total of 94 object categories which cover common objects such as animals, vehicles, accessories and persons in different activities.

      li The videos in our dataset are taken by both amateurs and professionals. Therefore, in addition to various object motion, there is frequently significant camera motion.

      li Our segmentation masks are carefully labeled by human annotators to ensure high quality

      p We expect that our new dataset shall bring new possibilities of generating novel ideas for dense-prediction video tasks as well as providing a more comprehensive evaluation methodologies for video segmentation technology.

      p Our workshop is co-located with another video segmentation workshop
        a(href="http://eecs.oregonstate.edu/IWVS_workshop/")  "The Third International Workshop on Video Segmentation"
        | . The other workshop will discuss on a wide range of topics in video segmentation. Welcome to attend their workshop as  well in the morning session.

    .section
      h1.title.is-4 Announcement
      ul
        li.has-text-weight-bold The test server is now ready at
          a(href="https://competitions.codalab.org/competitions/19544")  CodaLab.
        li The top three teams will be awarded with prizes.
        li The training dataset is available. Please checkout
          router-link(to="/dataset/download")  download
          |  page.
        li The test server will be available soon.

    .section
      h1.title.is-4 Tentative Timetable
      ul
        li <strong>Sep 14th</strong>: The workshop begins.
        li <strong>Aug 27th</strong>: The final competition results will be announced and high-performance teams will be invited.
        li <strong>Aug 10th-25th</strong>: Release the test dataset and open the submission of the test results.
        li <strong>Jul 18th</strong>: Setup the submission server on CodaLab and open the submission of the validation results.
        li <strong>Jun 18th</strong>: Release the training and validation dataset.

    // .section
    //   h1.title.is-4 Citation
    //   p Available soon!
      //p If you are reporting results of the challenge or using the dataset, Please cite:

    .section
      h1.title.is-4 Organizers
      .columns.flex-wrap
        div(v-for="organizer in organizers")
          figure.image.is-128x128.has-text-centered
            img.is-rounded(:src="'/static/organizers/'+organizer.im_name+'.jpg'")
          p.is-size-6.has-text-centered
            a(:href='organizer.link') {{organizer.name}}
            br
            span {{organizer.affiliation}}

    .section
      h1.title.is-4 Contact
      p For Challenge related questions, please feel free to contact
        a(href='mailto:ytvos@gmail.com')  ytbvos@gmail.com
        |.

    .section
      h1.title.is-4 Sponsors
      .columns.flex-wrap
        div(v-for="sponsor in sponsors")
          figure.image.is-128x128
            img(:src="'/static/sponsors/'+sponsor.im_name")
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'

@Component
export default class ChallengePage extends Vue {
  organizers = [
    {
      name:'Ning Xu',
      affiliation:'Adobe Research',
      im_name:'NingXu',
      link: 'http://sites.google.com/view/ningxu/',
    }, {
      name:'Linjie Yang',
      affiliation:'Snap Research',
      im_name:'LinjieYang',
      link: 'https://sites.google.com/site/linjieyang89/',
    }, {
      name:'Yuchen Fan',
      affiliation:'UIUC',
      im_name:'YuchenFan',
      link: 'https://ece.illinois.edu/directory/profile/yuchenf4',
    }, {
      name: 'Brian Price',
      affiliation: 'Adobe Research',
      im_name:'BrianPrice',
      link: 'https://www.brianpricephd.com/',
    }, {
      name: 'Weiyao Lin',
      affiliation: 'SJTU',
      im_name: 'WeiyaoLin',
      link: 'https://weiyaolin.github.io/',
    }, {
      name: 'Michael Ying Yang',
      affiliation: 'U of Twente',
      im_name: 'MichaelYingYang',
      link: 'https://sites.google.com/site/michaelyingyang/',
    }, {
      name: 'Jianchao Yang',
      affiliation: 'Toutiao AI Lab',
      im_name: 'JianchaoYang',
      link: 'http://www.ifp.illinois.edu/~jyang29/',
    }, {
      name: 'Jiebo Luo',
      affiliation: 'U of Rochester',
      im_name: 'JieboLuo',
      link: 'http://www.cs.rochester.edu/u/jluo/',
    }, {
      name: 'Thomas Huang',
      affiliation: 'UIUC',
      im_name: 'Tom',
      link: 'https://ece.illinois.edu/directory/profile/t-huang1'
    },
  ]
  sponsors = [
    {name:'Snapchat', im_name:'snapchat.jpg'},
    {name:'Adobe',  im_name:'adobe.png'},
    {name:'UIUC', im_name:'uiuc.jpg'},
    {name:'CAS', im_name:'cas.jpg'},
  ]
}
</script>
