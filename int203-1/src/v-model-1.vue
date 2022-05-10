<script setup>
import { ref } from 'vue'
const menu = ref([])
</script>
 
 <template>
    <div>
      <h2>select menu:</h2>
      <input type="checkbox" value="noodle" v-model="menu" />
      <label>noodle</label>
      <input type="checkbox" value="pizza" v-model="menu" />
      <label>pizza</label>
      <input type="checkbox" value="pancake" v-model="menu" />
      <label>pancake</label>
      <input type="checkbox" value="pudding" v-model="menu" />
      <label>pudding</label>

      <p>{{ menu }}</p>
    </div>

 </template>

 <style></style>