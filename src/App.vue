<template>
    <div class="app">
        <div class="header">
            Bibliography
        </div>
        <div class="main_container">
            <div class="list_authors">
                <h2> Авторы </h2>
                <div class="authors">
                    <form class="form_author" v-for="i in countAuthors">
                        <h3> Автор {{i}} </h3>
                        <input class="text" type="text" placeholder="Фамилия"> 
                        <input class="text" type="text" placeholder="Инициалы">
                    </form>
                </div>
                <div class="buttons">
                    <button class="button_author_add" @click="addAuthor"> Добавить автора </button>
                    <button class="button_author_del" @click="deleteAuthor"> Удалить автора </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            countAuthors: 1
        }
    },
    methods: {
        addAuthor(){
            this.countAuthors += 1
        },
        deleteAuthor(){
            if (this.countAuthors != 1) {
                this.countAuthors -= 1
            }
        }
    },
}
</script>

<style>
    *{
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        background-color: white;
    }

    .app{
        padding: 20px;
    }

    .header{
        width: 100%;
        height: 70px;
        background-color: #E2E2E2;
        box-shadow: 0 0 3px;
        font: normal 30px Georgia;
        padding: 15px 0 0 150px;
        margin-bottom: 30px;
    }

    h2, h3{
        padding: 10px 0px 10px 20px;
    }

    .list_authors{
        padding-left: 20px;
    }

    .authors{
        border: 1px solid #9F9F9F;
        border-radius: 10px;
        width: 100%;
        padding: 15px;

    }

    .form_author{
        border-bottom: 2px dotted #9F9F9F;
    }

    .text{
        width: 95%;
        border: 1px solid grey;
        padding: 10px 15px;
        margin: 0  0 20px 10px;
        font-size: 17px;
        border-radius: 12px
    }

    .buttons{
        padding: 0 0 0 20px;
    }

    .button_author_add, .button_author_del{
        font: normal 14px Georgia;
        width: 120px;
        height: 50px;
        color: white;
        margin: 10px;
        border: 1px solid rgb(131, 131, 131);
        border-radius: 10px;
        background: gray;
        box-shadow: 0 0 5px black;
        transition: all 500ms ease;
    } 

     
    .button_author_add:hover{
        background: rgba(76, 196, 72, 0.651);
        cursor: pointer;
        box-shadow: 0 0 3px rgba(0,0,0,0.5);
    }

    .button_author_del:hover{
        background: rgba(230, 47, 47, 0.651);
        cursor: pointer;
        box-shadow: 0 0 3px rgba(0,0,0,0.5);
    }

</style>