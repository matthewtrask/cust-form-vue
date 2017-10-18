<template>
  <div class="hello">
    <h1>Customer Complaint Form</h1>
    <form method="post" action="/addname">
      <section>
        <h2>Customer Information</h2>
        <div class="row">
          <div class="col-md-3"><input type="text" :id="firstname" name="firstName" placeholder="First Name"></div>
          <div class="col-md-3"><input type="text" :id="lastname" name="lastName" placeholder="Last Name"></div>
          <div class="col-md-3"><input type="email" :id="email" name="email" placeholder="Email Address"></div>
        </div>
        <div id="locationField" class="row">
          <div class="col-md-12"><input id="autocomplete" v-model.lazy="filled" placeholder="Enter your address" onFocus="geolocate()" type="text"></input>
          </div>
        </div>
        <div class="row">
          <div class="col-md-2"><input id="street_number" placeholder="Street Number" name="streetNum" disabled="true"></input>
          </div>
          <div class="col-md-10"><input id="route" placeholder="Street" name="street" disabled="true"></input>
          </div>
        </div>
        <div class="row">
          <div class="col-md-2"><input id="locality" placeholder="City" name="city" disabled="true"></input>
          </div>
          <div class="col-md-2"><input id="administrative_area_level_1" name="state" placeholder="State" disabled="true"></input>
          </div>
          <div class="col-md-2"><input id="postal_code" placeholder="Zip Code" name="zipCode" disabled="true"></input>
          </div>
          <div class="col-md-6"><input id="country" placeholder="United States" name="country" disabled="true"></input>
          </div>
        </div>
      </section>
      <section id="bottom-section" v-if="filled">
        <h2>Customer Grievence</h2>
        <div class="row">
          <div class="col-md-3">
            <input type="text" name="dept" placeholder="Department">
          </div>
          <div class="col-md-9">
            <input type="text" name="location" placeholder="Location">
          </div>
        </div>
        <div class="row">
          <div class="col-md-12">
            <textarea rows="5" name="description" placeholder="description of problem" cols="50"></textarea>
          </div>
          <div class="col-md-12">
            <input type="submit" value="Add Name">
          </div>
        </div>
      </section>
    </form>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  text-align: center;
  margin: 2.2em 0 0;
}
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
