<template>
  <div class="page">
    <div>
      <navbar />
    </div>
    <div>
      <h1>Coursework materials</h1>
    </div>
  </div>
</template>
<script>
import navbar from '../../components/navbar.vue'
export default {
  components: { navbar },
  data() {
    return {
      units: [
        {
          id: 1,
          unitName: 'Unit 1',
          unitDescription: 'Unit one of the entire course',
          unitMaterials: [
            {
              title: 'Topic One',
              url: 'https://google.com',
              topicDescription:
                "Don't worry about much, you'll learn more later"
            },
            {
              title: 'Topic Two',
              url: 'https://google.com',
              topicDescription:
                "Don't worry about much, you'll learn more later"
            }
          ]
        },
        {
          id: 2,
          unitName: 'Unit 2',
          unitDescription: 'Unit one of the entire course',
          unitMaterials: [
            {
              title: 'Topic One',
              url: 'https://google.com',
              topicDescription:
                "Don't worry about much, you'll learn more later"
            },
            {
              title: 'Topic Two',
              url: 'https://google.com',
              topicDescription:
                "Don't worry about much, you'll learn more later"
            }
          ]
        }
      ]
    }
  }
}
</script>
<style scoped>
</style>