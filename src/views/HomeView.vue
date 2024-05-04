<template>
  <div class="card">
  <div class="card-header">
    Featured
  </div>
  <div class="card-body">
    <table class="table">
  <thead>
    <tr >
      <th scope="col">#</th>
      <th >OrderID</th>
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
  <tbody>
    <tr v-for="rep in resports" :key="rep.OrderID">
      <th scope="row">{{rep.ProductID }}</th>
      <td>{{ rep.CustomerID }}</td>
      <td>{{ rep.OrderDate }}</td>
      <td>@mdo</td>
    </tr>
  </tbody>
</table>
  </div>
</div>
</template>
<script>
    import axios from 'axios';
    export default{
      data(){
        return { resports:null}
      },
      mounted(){
        this.getReport();
      },
      methods:{
         getReport(){
           axios.get('https://localhost:7108/api/SalesReport').then(
            response => (
              this.resports = response.data
            )
          )
        }
      }
    }
</script>


