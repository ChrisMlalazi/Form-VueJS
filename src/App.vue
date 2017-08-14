<template>
    <div class="container">
        <form v-if="!submitted">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->

                    <!-- Full Name (First Name + Last Name) -->
                    <label for="fullname">Full Name</label>
                    <input 
                    type="text" id="fullname" 
                    class="form-control"
                    v-model="userData.fullname">
                    
                    <!-- Mail -->
                    <label for="email">Mail</label>
                    <input 
                    type="text" id="email" 
                    class="form-control"
                    v-model="userData.email">

                    <!-- Password -->
                    <label for=password>Password</label>
                    <input 
                    type="password" id="password" 
                    class="form-control"
                    v-model="userData.password">

                    <!-- Store Data? Yes/No -->
                    <label for="data">
                        <input type="radio" 
                        id="data"
                        value="Yes"
                        v-model="choice">Yes     
                    </label>

                    <label for="data">
                        <input type="radio" 
                        id="data"
                        value="No"
                        v-model="choice">No     
                    </label>
                    
                  <!--   Submit Button -->
                    <div class="row">
                
                    <button
                            type="submit" class="btn btn-primary"
                            @click.prevent="submitted = true">Submit!
                    </button>
              
            </div>
                    

                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="submitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ userData.fullname }}</p>
                        <p>Mail: {{ userData.email }}</p>
                        <p>Password: {{ userData.password }}</p>
                        <p>Store in Database?: {{ choice }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                userData: {
                    fullname: '',
                    email: '',
                    password: ''
                },
                choice: 'Yes',
                submitted: false
            }
        }
    }
</script>

<style>
  .container {
    background-color: coral;
    margin-top: 50px;
    padding-top: 50px;

  }
</style>







