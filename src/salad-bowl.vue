<template>
  <div>
    <div>
      <ul>
        <li v-for="item in salad">{{ item }}</li>
      </ul>
    </div>
    <form>
      <input v-model="extraIngredient"
            type="text"
      />
      <button type="submit" @click="addExtraIngredient">Add</button>
    </form>
  </div>
</template>

<script>
import { mapActions } from 'vuex'

export default {
  data() {
    return {
      ...this.$store.state,
      extraIngredient: ''
    }
  },

  methods: {
    ...mapActions(['addIngredient']),
    addExtraIngredient: function() {
      this.addIngredient(this.extraIngredient)
      this.extraIngredient = ''
    }
  },
}
</script>
