<template>
    <div id="main_dash">
        <div id="left_con">
            <Navbar></Navbar>
        </div>
        <div id="middle_con">
           <MainContent>
               <div slot="heading">
                   <p id="head_title">Farmers</p>
                   <p id="head_descript">Here is a list of the registered farmers across the island.</p>
               </div>
               <div id="table" slot="table">
                   <BigTable :headers="farm_table.headers" :tdata="farm_table.data" :addCrop="false" :searchB="true" ncheck="Farmers"></BigTable>
               </div>
           </MainContent>

        </div>
        <div id="right_con">
            <Qpanel></Qpanel>

        </div>
    </div>
</template>

<script>
import Navbar from './Navbar'
import MainContent from './MainContent'
import Qpanel from './Qpanel'
import BigTable from './BigTable'

export default {
    name:"Farmers",
    components:{
        Navbar,
        MainContent,
        Qpanel,
        BigTable
        },
    data(){
        return {
            farm_table:{
                headers:['Name','Farm', 'Trn','Contact','Parish','District','Created'],
                data:[
                    {
                        name:'Ruppert Baxton', 
                        farm:'Rupps Hens',
                        trn:'38597864',
                        contact:'8763948587',
                        parish:'St.James',
                        district:'Gordon Village',
                        date:'6-19-20'
                    },
                    {
                        name:'Ruppert Baxton', 
                        farm:'Rupps Hens',
                        trn:'83746572',
                        contact:'8763948587',
                        parish:'St.James',
                        district:'Gordon Village',
                        date:'6-19-20'
                    },
                    {
                        name:'Ruppert Baxton', 
                        farm:'Rupps Hens',
                        trn:'83746572',
                        contact:'8763948587',
                        parish:'St.James',
                        district:'Gordon Village',
                        date:'6-19-20'
                    }
                ]
            }
        }
    }

}
</script>
<style scoped>
#main_dash
{
    position: absolute;
    display: grid;
    grid-template-columns: 250px auto 30%;
    width: 100vw;
    height: 100vh;
    top: 0px;
    left: 0px;
}
#middle_con
{
    display:flex;
    flex-direction: column;
    align-items: center;
}
#main_content_con
{
    position: relative;
    width: 90%;
    top:80px;
}

#head_title
{
    font-family: 'Lato', sans-serif;
    font-weight: bolder;
    font-size:40px;
    margin: 0px;
}
#head_descript
{
    margin: 0px;
    font-family: 'Lato', sans-serif;
    font-size: 25px;
    color: rgb(212, 212, 212);
    
}
#table
{
    position: relative;
    margin-top: 15px;
}
</style>