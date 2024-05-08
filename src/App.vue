<template>
    <div>
        <div>
            <form class="form" @submit.prevent>
                <input type="text" placeholder="Название поста" v-bind:value="title" @input="title = $event.target.value">
                <input type="text" placeholder="Описание поста" v-bind:value="body" @input="body = $event.target.value">
                <button class="btn" @click="createPost">Создать пост</button>
            </form>
        </div>
        <div class="post" v-for="post in posts" :key="post.id">
        <div>
            <strong>Название: </strong>{{post.title}}
        </div>
        <div>
            <strong>Описание: </strong>{{post.description}}
        </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            posts: [
                {id: 1, title: 'Post 1',description: 'Description 1'},
                {id: 2, title: 'Post 2',description: 'Description 2'},
                {id: 3, title: 'Post 3',description: 'Description 3'},
            ],
            title: '',
            body: ''
        }
    },
    methods: {
        createPost(){
            this.posts.push({id: Date.now(), title: this.title, description: this.body})
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
    width: 300px;
}
.form{
    display: flex;
    flex-direction: column;
    gap: 10px;
    width: 300px;
}
.form input{
    height: 40px;
    padding: 5px 10px;
    border: none;
    border-radius: 5px;
    background-color: rgb(233, 233, 233);
    outline: none;
}
.btn{
    height: 40px;
    border: none;
    border-radius: 5px;
    background-color: teal;
    width: 100%;
    cursor: pointer;
    color: white;
    transition: 0.3s;
}
.btn:hover{
    background-color: rgb(0, 68, 68);
}
</style>