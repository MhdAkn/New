<template>
  <div class="inscription2">
       <nav class="navbar navbar-light bg-light">
            <div class="container-fluid">
                <a class="navbar-brand"><img class="img-responsive " alt="Vue logo" src="../assets/logoSite.jpg"></a>
                <form class="d-flex">
                <router-link  class="btn btn-primary" to="/inscription2">Inscription</router-link>
                <router-link  class="btn btn-outline-primary" to="/connexion">Connexion</router-link>
                </form>
            </div>
     </nav>
      <h5 class="text-primary" style="text-align:center; margin-top:25px" ><b> INSCRIPTION </b></h5>
   
            <form row g-3 method="POST" @submit.prevent="submitHandler" > 

            <fieldset  class="border p-2">

                <legend  class="float-none w-auto p-3"><h5 class="text-primary" style="text-align:center" >Information financière de l'entreprise</h5></legend>

                <fieldset class="border p-2">
                    <legend  class="float-none w-auto p-3"><h5 class="text-primary" style="text-align:center" >Equipes dirigeantes</h5></legend>
                    <div class="row  d-flex flew-wrap justify-content-center"  >
                        <div class="col-sm-3 mb-3 ">
                             <div class="input-group">
                                   <span class="input-group-text bg-white" id="basic-addon1" style="border-right: none;">
                                        <img src="../assets/person-square.svg" alt="">,
                                    </span>
                                <input class="form-control" id="nom" type="text" placeholder="Nom" required>
                            </div>
                        </div>
                        <div class="col-sm-3 mb-3">
                            <div class="input-group">
                                    <span class="input-group-text bg-white" id="basic-addon1">
                                        <img src="../assets/Place Marker.svg" alt="">
                                    </span>
                                    <select class="form-select" id="teamPosition" required >
                                        <option selected>Position</option>
                                        <option value="CEO">CEO</option>
                                        <option value="CTO">CTO</option>
                                        <option value="COO">COO</option>
                                    </select>
                            </div>
                        </div>
                        <div class="col-sm-3 mb-3">
                             <div class="input-group">
                                   <span class="input-group-text bg-white" id="basic-addon1" style="border-right: none;" >
                                        <img src="../assets/Link.svg" alt="">
                                    </span>
                                <input class="form-control" id="url" type="url" placeholder="Url" required>
                            </div>
                        </div>
                        <div class="col-sm-1 mb-3">
                            <div class="input-group">
                                    <span class=" bg-white" id="basic-addon1" @click="addTeam">
                                        <img src="../assets/Add circle.svg" alt="">
                                    </span>
                            </div>
                        </div>
                
                    </div>
                </fieldset>
                <fieldset class="border p-2">
                    <legend  class="float-none w-auto p-3"><h5 class="text-primary" style="text-align:center" >Investisseurs</h5></legend>
                    <div class="row   d-flex flew-wrap justify-content-center">
                        <div class="col-sm-3 mb-3">
                             <div class="input-group">
                                 <span class="input-group-text bg-white" id="basic-addon1" style="border-right: none;">
                                    <img src="../assets/person-square.svg" alt="">
                                </span>
                                <input class="form-control" id="nomI" type="text" placeholder="Nom" required>
                            </div>
                        </div>
                        <div class="col-sm-3 mb-3">
                            <div class="input-group">
                                <span class="input-group-text bg-white" id="basic-addon1">
                                    <img src="../assets/Place Marker.svg" alt="">
                                </span>
                                    <select class="form-select" id="posI" placeholder="Position" required>
                                        <option selected>Position</option>
                                        <option value="CEO">CEO</option>
                                        <option value="CTO">CTO</option>
                                        <option value="COO">COO</option>

                                    </select>
                            </div>
                        </div>
                        <div class="col-sm-3 mb-3">
                             <div class="input-group">
                                <span class="input-group-text bg-white" id="basic-addon1" style="border-right: none;">
                                    <img src="../assets/Link.svg" alt="">
                                </span>
                                <input class="form-control" id="urlI" type="url" placeholder="Url" required >
                            </div>
                        </div>
                        <div class="col-sm-1 mb-3">
                            <div class="input-group">
                                <span class=" bg-white" id="basic-addon1" @click="addInvestissor">
                                    <img src="../assets/Add circle.svg" alt="" >
                                </span>
                            </div>
                        </div>
                
                    </div>
                </fieldset>
                <fieldset class="border p-2">
                    <legend  class="float-none w-auto p-3"><h5 class="text-primary" style="text-align:center" >Chiffres d'affaires</h5></legend>
                    <div class="row   d-flex flew-wrap justify-content-center">
                        <div class="col-sm-4 mb-4">
                            <div class="input-group">
                                    <span class="input-group-text bg-white" id="basic-addon1">
                                        <img src="../assets/table.svg" alt="">
                                    </span>
                                <input class="form-control" id="anneeCa" type="date" placeholder="Année" required>
                            </div>
                        </div>
                        <div class="col-sm-5 mb-4">
                            <div class="input-group">
                                    <span class="input-group-text bg-white" id="basic-addon1">
                                        <img src="../assets/Table of Content.svg" alt="">
                                    </span>
                                <input class="form-control" id="montantCa" type="text" placeholder="Montant"  v-model="chiffre_affaire.montant" required>
                            </div>
                        </div>
                         <div class="col-sm-1 mb-3">
                            <div class="input-group">
                                <span class=" bg-white" id="basic-addon1" @click="addCa">
                                    <img src="../assets/Add circle.svg" alt="" >
                                </span>
                            </div>
                        </div>
                    </div>
                </fieldset>
                 <fieldset class="border p-2">
                    <legend  class="float-none w-auto p-3"><h5 class="text-primary" style="text-align:center" >Levés de fonds</h5></legend>
                    <div class="row   d-flex flew-wrap justify-content-center">
                        <div class="col-sm-4 mb-4">
                            <div class="input-group">
                                    <span class="input-group-text bg-white" id="basic-addon1">
                                        <img src="../assets/table.svg" alt="">
                                    </span>
                                <input class="form-control" id="anneelf" type="date" placeholder="Année" required>
                            </div>
                        </div>
                        <div class="col-sm-5 mb-4">
                            <div class="input-group">
                                    <span class="input-group-text bg-white" id="basic-addon1">
                                        <img src="../assets/Table of Content.svg" alt="">
                                    </span>
                                <input class="form-control" id="montantlf" type="text" placeholder="Montant" required>
                            </div>
                        </div>
                        <div class="col-sm-1 mb-3">
                            <div class="input-group">
                                <span class=" bg-white" id="basic-addon1" @click="addLf">
                                    <img src="../assets/Add circle.svg" alt="">
                                </span>
                            </div>
                        </div>
                    </div>
                </fieldset>
                    <div class="row gx-3 gy-2 align-items-center" style="margin-left: 4px">
                        <div class="col-sm-2 mb-4">
                            <div class="input-group">
                                    <span class="input-group-text bg-white" id="basic-addon1">
                                        <img src="../assets/dollar.svg" alt="">
                                    </span>
                                <input class="form-control" id="capital" type="text" placeholder="Capital Social" required>
                            </div>
                        </div>
                    </div>
            </fieldset>
                <br><br><br>
                 <div class="position-relative">
                    <div class="position-absolute bottom-0 start-0"><router-link  class="btn btn-primary previous pull-left" to="/inscription1">&#8249; Précédent</router-link></div>
                <div class="position-absolute bottom-0 end-0"><button class="btn btn-primary next pull-right" type="Submit">Suivant &#8250;</button></div>
                </div>
            </form>

            <div>
</div>
  </div>
  
</template>
<script>

    import { mapState} from 'vuex'
    export default 
    {
        name:'Inscription2View',
        computed:
        {
            ...mapState(['startup'])
                      
        },
        data()
        {
            return {

            chiffre_affaire:
            {
                annee: null,
                montant: null
            },
            levee_fonds:
            {
                annee: null,
                montant: null
            }
                  }
        },
        methods:
        { 
            addTeam()
            {
                let nomInput = document.getElementById("nom") 
                let urlInput = document.getElementById("url")
                let positionInput = document.getElementById("teamPosition").value
                
                this.startup.list_team.push({ name: nomInput.value, position: positionInput, url: urlInput.value})
                alert("Enrégistrement reussi")
            },
            addInvestissor()
            {
                let nomInput = document.getElementById("nomI") 
                let urlInput = document.getElementById("urlI")
                let positionInput = document.getElementById("posI").value
                
                this.startup.list_investissors.push({ name: nomInput.value, position: positionInput, url: urlInput.value})
                alert("Enrégistrement reussi")
            },
            addCa()
            {
                let a = document.getElementById("anneeCa") 
                let m = document.getElementById("montantCa")
                
                this.startup.turnover.push({ annee: a.value, montant: m.value})
                alert("Enrégistrement reussi")
            },
            addLf()
            {
                let a = document.getElementById("anneelf") 
                let m = document.getElementById("montantlf")
                
                this.startup.fundings.details.push({ annee: a.value, montant: m.value})
                alert("Enrégistrement reussi")
            },
            submitHandler()
            {
                console.warn(this.startup) 
                this.$router.push("inscription3")
            }
        }
}
</script>
<style scoped>
fieldset {
    border: 2px solid  #ddd !important;
    padding: 0 1.4em 1.4em 1.4em !important;
    margin: 10px 10px;
  }
  .last{
         margin-left: 25px ;
  }
.previous,.next{   
     margin: 15px 15px;

    text-decoration: none;
   
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
input,select{
    border-left: none;
}

</style>