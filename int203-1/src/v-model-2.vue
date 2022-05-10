<script setup>
console.clear();
import { ref } from "vue";
const picked = ref("");
</script>
 
 <template>
  <div>
    <h2>what gender are you?</h2>
    <input type="radio" value="Male" v-model="picked" />
    <label for="Male">Male</label><br />
    <input type="radio" value="Female" v-model="picked" />
    <label for="Female">Female</label><br />
    <input type="radio" value="Others" v-model="picked" />
    <label for="others">Others</label><br />
    <span>Picked: {{ picked }}</span>
  </div>
</template>

 <style></style>