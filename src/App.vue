<template>
    <div class="post">
      <div>
        <strong>Название:</strong>Пост о javascript
      </div>
      <div>
        <strong>Описание:</strong>JavaScript универсальный язык программирования.
      </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            posts: [
                {id: 1, title: 'Post 1',description: 'Description 1'},
            ]
        }
    }
}
</script>

<style scoped>
*{
    margin: 0;  
    padding: 0;
    box-sizing: border-box;
}
.post{
    display: flex;
    flex-direction: column;
    gap: 10px;
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
}
</style>