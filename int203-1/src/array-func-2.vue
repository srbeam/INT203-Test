<script setup>
const students = [
  {id:1, name:'Somsri', gpa: 3.5},
  {id:2, name:'Somchai', gpa: 3.1},
  {id:3, name:'Somsong', gpa: 2.7}
]
const good = students.filter((student) => {
  return student.gpa > 3
})
</script>
 
 <template>
<div>
  <p>{{good}}</p>
</div>
</template>

 <style></style>