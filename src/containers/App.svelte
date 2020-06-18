<script>
    import { onMount } from "svelte";
    import Header from '../components/Header.svelte';
    import Main from '../components/Main.svelte';
    import Sidebar from '../components/Sidebar.svelte';
    import TimeLine from '../components/TimeLine.svelte';

    let data = {};
    const API = 'https://us-central1-pugstagram-co.cloudfunctions.net/data';
    onMount(async()=>{
        console.log('get data');
        const response = await fetch(API);
        //data = await response.json();

        const jsonData = {
                            "posts":[
                                {
                                    "username":"aeco77",
                                    "location":"Monterrey, Nuevo León",
                                    "avatar":"https://sumedico.blob.core.windows.net/images/2020/03/17/cuidadosgatobebe_2-focus-min0.07-0.45-983-557.jpg",
                                    "photo":"https://sumedico.blob.core.windows.net/images/2020/03/17/cuidadosgatobebe_2-focus-min0.07-0.45-983-557.jpg",
                                    "like":false,
                                    "postComment":"Disfrutando el día",
                                    "bookmark":false,
                                    "comments":[
                                        {
                                        "id":1,
                                        "text":"Hola",
                                        "username":"CatDog"
                                        },
                                        {
                                        "id":2,
                                        "text":"Hola buen día",
                                        "username":"Kitty"
                                        }
                                    ]
                                },
                                {
                                    "username":"aeco77",
                                    "location":"Monterrey, Nuevo León",
                                    "avatar":"https://sumedico.blob.core.windows.net/images/2020/03/17/cuidadosgatobebe_2-focus-min0.07-0.45-983-557.jpg",
                                    "photo":"https://img.youtube.com/vi/T5utMGMdNec/hqdefault.jpg",
                                    "like":false,
                                    "postComment":"Disfrutando el día",
                                    "bookmark":false,
                                    "comments":[
                                        {
                                        "id":1,
                                        "text":"Hola",
                                        "username":"CatDog"
                                        },
                                        {
                                        "id":2,
                                        "text":"Hola buen día",
                                        "username":"Kitty"
                                        }
                                    ]
                                },
                                {
                                    "username":"aeco77",
                                    "location":"Monterrey, Nuevo León",
                                    "avatar":"https://sumedico.blob.core.windows.net/images/2020/03/17/cuidadosgatobebe_2-focus-min0.07-0.45-983-557.jpg",
                                    "photo":"https://diseñoscreativos.com/wp-content/uploads/2018/06/imagenes-de-gatos-negros-www.dise%C3%B1oscreativos.com-portada-2-e1528765413541.jpg",
                                    "like":false,
                                    "postComment":"Disfrutando el día",
                                    "bookmark":false,
                                    "comments":[
                                        {
                                        "id":1,
                                        "text":"Que taaal!!",
                                        "username":"CatDog"
                                        },
                                        {
                                        "id":2,
                                        "text":"Hola buen día",
                                        "username":"Kitty"
                                        }
                                    ]
                                },
                                {
                                    "username":"aeco77",
                                    "location":"Sán Nicolas, Nuevo León",
                                    "avatar":"https://sumedico.blob.core.windows.net/images/2020/03/17/cuidadosgatobebe_2-focus-min0.07-0.45-983-557.jpg",
                                    "photo":"https://sumedico.blob.core.windows.net/images/2020/03/17/cuidadosgatobebe_2-focus-min0.07-0.45-983-557.jpg",
                                    "like":false,
                                    "postComment":"Disfrutando el día",
                                    "bookmark":false,
                                    "comments":[
                                        {
                                        "id":3,
                                        "text":"jajaja",
                                        "username":"CatDog"
                                        },
                                        {
                                        "id":2,
                                        "text":"Hola buen día",
                                        "username":"Kitty"
                                        }
                                    ]
                                }
                            ],   
                            "user":{
                                "nickname":"aeco77",
                                "name":"Angel Cortez"
                                }
                            };
                            data= jsonData;
console.log(jsonData);
console.log(data);
    })
</script>

<style> 
    @import url('https://fonts.googleapis.com/css2?family=Lato:wght@300;400&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');
    :global(body){
        background-color: #fafafa;
        color:rgba(38,38,38,0,7);
        font-family: "Lato", sans-serif;
        margin: 0;
        padding:0;
    }

    :global(h1,h2,h3){
        margin:0;
        padding:0;
        
    }
</style>

<Header/>
<Main>
    <TimeLine posts={data.posts}/>
    <Sidebar {...data.user}/>
</Main>