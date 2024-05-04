
import DataTable from 'datatables.net-bs5';
<template>
    <div class="row">
        <div class="col-lg-8 offset-lg-2">
            <div class="table-responsive">
                <DataTable :data="report" :columns="columns" class="table table-striped table-bordered display"
                :options="{responsive:false,autoWidth:true,dom:'Bfrtip'}">
                    <thead>
                        <tr>
                            <th>#</th>
                            <th>OrderID</th>
                            <th>OrderDate</th>
                            <th>CustomerID</th>
                            <th>ProductID</th>
                            <th>ProductName</th>
                            <th>CategoryName</th>
                            <th>UnitPrice</th>
                            <th>Quantity</th>
                            <th>TotalPrice</th>
                            <th>SalesPersonID</th>
                            <th>SalesPersonName</th>
                            <th>ShippingAddres</th>
                            <th>City</th>
                            <th>BillAddressId</th>

                        </tr>
                    </thead>
                </DataTable>
            </div>
        </div>
    </div>
</template>
<script>
import axios from "axios";
import DataTable from 'datatables.net-vue3';
import DataTableLib from 'datatables.net-bs5'
import Buttons from 'datatables.net-buttons-bs5'
import ButtonsHtml5 from 'datatables.net-buttons/js/buttons.html5'
import print from 'datatables.net-buttons/js/buttons.print'
import pdfmake from 'pdfmake';
import pdfFonts from 'pdfmake/build/vfs_fonts';
import 'datatables.net-responsive-bs5';
import JsZip from 'jszip';
window.JsZip = JsZip;
DataTable.use(DataTableLib);
DataTable.use(pdfmake);
DataTable.use(ButtonsHtml5);

export default{
    components:{DataTable},
    data(){
        return{
            report: null,
                        columns:[
                {data:null, render: function(data,type,row,meta)
                    {return `${meta.row+1}`}},
                    {data:'OrderID'},
                    {data:'orderid'},
                    {data:'orderid'},
                    {data:'orderid'},
                    {data:'orderid'},
                    {data:'orderid'},
                    {data:'orderid'},
                    {data:'orderid'},
                    {data:'orderid'},
                    {data:'orderid'},
                    {data:'orderid'},
                    {data:'orderid'},
                    {data:'orderid'},
                    {data:'orderid'},
                    
                    
            ],

        }
    },
    mounted(){
        this.getReport();
    },
    methods:{
        getReport(){
            axios.get('https://localhost:7108/api/SalesReport').then(
                response =>(
                    this.report = response.data
                )
            );
        }
    }
}

</script>
<style>
@import 'datatables.net-bs5'
</style>