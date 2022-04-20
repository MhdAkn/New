<template>
  <div class="inscription3">
      <nav class="navbar navbar-light bg-light">
            <div class="container-fluid">
                <a class="navbar-brand"><img class="img-responsive " alt="Vue logo" src="../assets/logoSite.jpg"></a>
                <form class="d-flex" method="POST" action="/inscription4">
                <router-link  class="btn btn-outline-primary" to="/inscription2">Inscription</router-link>
                <router-link  class="btn btn-outline-primary" to="/connexion">Connexion</router-link>
                </form>
            </div>
     </nav>
     <h3 class="text-primary" style="text-align:center" >INSCRIPTION</h3>
            <form row g-3 action="/inscription3" @submit.prevent="submitHandler"  method="post" > 
                <fieldset class="border p-2">
                    <legend  class="float-none w-auto p-3"><h5 class="text-primary" style="text-align:center" >Information de l'entreprise</h5></legend>
                    <div class="row gx-3 gy-2 align-items-center">
                        <div class="col-sm-6 mb-3">
                             <div class="input-group">
                                   <span class="input-group-text bg-white" style="border-right: none;" id="basic-addon1">
                                        <img src="../assets/person-square.svg" alt="">
                                    </span>
                                <input  v-model="startup.connexion_datas.username" class="form-control" id="username" type="text" placeholder="Username"  required>
                            </div>
                        </div>
                        <div class="col-sm-6 mb-3">
                            <div class="input-group">
                                    <span class="input-group-text bg-white" id="basic-addon1">
                                        <img src="../assets/Lock.svg" alt="">
                                    </span>
                                <input v-model="startup.connexion_datas.password" class="form-control" id="password" type="password" minlength="4" maxlength="8" pattern="[0-9a-zA-Z]{4,8}" placeholder="Password" required>
                                  
                           
                            </div>
                          
                        </div>
                
                    </div>
                    <br>
                     <div class="row gx-3 gy-2 align-items-center">
                        <div class="col-sm-6 mb-3">
                            <div class="input-group">
                                   <span class="input-group-text bg-white" id="basic-addon1">
                                        <img src="../assets/mail.svg" alt="">
                                    </span>
                                <input  v-model="startup.connexion_datas.second_email" class="form-control" id="emailRecuperation" type="email" placeholder="Email de récupération" required>
                            </div>
                            
                        </div>
                    </div>
                </fieldset>
                <fieldset class="border p-2">
                    <legend  class="float-none w-auto p-3"><h5 class="text-primary" style="text-align:center" >Information réseaux sociaux de l'entreprise</h5></legend>
                    <div class="row gx-3 gy-2 align-items-center">
                        <div class="col-sm-6 mb-3">
                            <div class="input-group">
                                    <span class="input-group-text bg-white" id="basic-addon1">
                                        <img src="../assets/Link.svg" alt="">
                                    </span>
                                <input class="form-control" id="urlfacebook" type="url" placeholder="Url de Facebook"  v-model="startup.facebook_url" required>
                            </div>
                        </div>
                        <div class="col-sm-6 mb-3">
                            <div class="input-group">
                                    <span class="input-group-text bg-white" id="basic-addon1">
                                        <img src="../assets/Link.svg" alt="">
                                    </span>
                                <input class="form-control" id="urllinkedin" type="url" placeholder="Url de Linkedin"  v-model="startup.linkedin_url" required>
                            </div>
                        </div>
                
                    </div>
                    <br>
                     <div class="row gx-3 gy-2 align-items-center">
                        <div class="col-sm-6 mb-3">
                            <div class="input-group">
                            <span class="input-group-text bg-white" id="basic-addon1">
                                       <img src="../assets/Link.svg" alt="">
                                    </span>
                                <input class="form-control" id="urlinstagram" type="url" placeholder="Url d'Instagram"  v-model="startup.instagram_url" required>  
                            </div>
                        </div>
                        <div class="col-sm-6 mb-3">
                            <div class="input-group">
                            <span class="input-group-text bg-white " id="basic-addon1">
                                       <img src="../assets/Link.svg" alt="">
                                    </span>
                                <input class="form-control" id="urltwiter" type="url" placeholder="Url de Twiter" v-model="startup.twitter_url" required>
                            </div>
                        </div>
                    </div>
                </fieldset>
                <br><br><br>
                <div>
                </div>
                 <div class="position-relative">
                <div class="position-absolute bottom-0 start-0"><router-link  class="btn btn-outline-primary previous pull-left" to="/inscription2">&#8249; Précédent</router-link></div>
                <div class="position-absolute bottom-0 end-0"><button type="submit" class="btn btn-primary next pull-right" to="/inscription3" >Suivant &#8250;</button></div>
                </div>
            </form>
  </div>
  
</template><script>
import { mapState} from 'vuex'
export default {
    name:'Inscription3View',
        computed:
        {
           ...mapState(['startup']),
        },
    data(){
        return{
        }
    },
    
    methods:
    {
        getDate()
        {
            let d = new Date();
            return d;
        },
            submitHandler()
            {
                console.warn(this.startup)
            }
       

    }
}
</script>
<style scoped>
fieldset {
    border: 2px solid  #ddd !important;
    padding: 0 1.4em 1.4em 1.4em !important;
    margin: 25px 25px;
  }
.has_required{
    text-decoration: line-through;
    color:#689868;
}
.previous,.next{   
     margin: 15px 15px;

    text-decoration: none;
}
input{
    border-left:0px
}
.has_required{
    text-decoration: line-through;
    color:#689868;
}
a {
  margin-right: 15px ;
  text-decoration: none;
  display: inline-block;
}
h3{
    margin-top: 25px;
}
.round {
  border-radius: 70%;
}

</style>
