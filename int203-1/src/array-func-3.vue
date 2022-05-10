<script setup>
const profiles = [
  {id:1, name:'Ball', age: 10},
  {id:2, name:'Jib', age: 16},
  {id:3, name:'Somsak', age: 35}
]
const childhood = profiles.find((profile) => {
  return profile.age > 1
})
const youthful = profiles.find((profile) => {
  return profile.age >15 
})
const adult = profiles.find((profile) => {
  return profile.age > 25
})
</script>
 
 <template>
<div>
  <p>Childhood: {{childhood}}</p>
  <p>Youthful: {{youthful}}</p>
  <p>Adult: {{adult}}</p>
</div>
</template>

 <style></style>