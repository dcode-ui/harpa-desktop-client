<template>
    <div id="main_dash">
        <div id="left_con">
            <Navbar></Navbar>
        </div>
        <div id="middle_con">
           <MainContent>
               <div slot="heading">
                   <p id="head_title">Crop Yields</p>
                   <p id="head_descript">Here is a list of the crop yields processes by the calculator.</p>
               </div>
               <div id="table" slot="table">
                   <BigTable :headers="farm_table.headers" :tdata="farm_table.data" :addCrop="false" :searchB="true" ncheck="Crop_Yield"></BigTable>
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
    name:"Crop_Yield",
    components:{
        Navbar,
        MainContent,
        Qpanel,
        BigTable
        },
    data(){
        return {
            farm_table:{
                headers:['Crop','Crop Type','Cost(lbs)','YieldPMS','Revenue PMS','Created'],
                data:[
                    {
                        crop:'Sweet Pepper', 
                        crop_type:'Vegetable',
                        cost:'200.00',
                        yield_pms:'40',
                        revenue_pms:'8000',
                        created:'6-19-20'
                    },
                    {
                        crop:'Peas', 
                        crop_type:'Legumes',
                        cost:'120.00',
                        yield_pms:'20',
                        revenue_pms:'2000',
                        created:'6-19-20'
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
</style>