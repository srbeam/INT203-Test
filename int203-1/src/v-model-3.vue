<script setup>
console.clear();
import { ref } from "vue";
const details = ref("");
</script>
 
 <template>
<div>
      Detail:
      <textarea
        v-model="details"
        cols="20"
        rows="1"
        placeholder="optional..."
      ></textarea>
      <p>{{ details }}</p>
    </div>
</template>

 <style></style>