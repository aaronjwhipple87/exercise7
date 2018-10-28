<template>
    <div class="container">
        <form>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <!-- Part 1 5 Points-->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <h1>Signup</h1>
                    <hr>
                    <!-- Full Name (First Name + Last Name) -->
                    <div class="form-group">
                        <label for="name">Name(First + Last):</label>
                        <input
                                type="text"
                                id="name"
                                class="form-control"
                                v-model="userData.name">
                    </div>
                    <!-- Mail -->
                    <div class="form-group">
                        <label for="email">Mail</label>
                        <input
                                type="text"
                                id="email"
                                class="form-control"
                                v-model="userData.email">
                    </div>
                    <!-- Password -->
                    <div class="form-group">
                        <label for="password">Password</label>
                        <input
                                type="password"
                                id="password"
                                class="form-control"
                                v-model.lazy.trim.number="userData.password">
                        <p>{{ userData.password }}</p> </div>

                    <!-- Store Data? Yes/No -->
                    <div class="form-group">Store Data?
                        <label for="yes">
                            <input
                                    type="radio"
                                    id="yes"
                                    value="Yes"
                                    v-model="storeData"> Yes
                        </label>
                        <label for="no">
                            <input
                                    type="radio"
                                    id="no"
                                    value="No"
                                    v-model="storeData"> No
                        </label>
                    </div>

                    <!-- Part 2 5 Points -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->
                    <div class="row">
                        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                            <button
                                    class="btn btn-primary"
                                    @click.prevent="submitted">Submit!
                            </button>
                        </div>
                    </div>

                    <!-- Part 3 5 Points -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                    <div class="form-group">
                        <label for="name">Name:</label>
                        <input
                                type="text"
                                id="firstName"
                                class="form-control"
                                v-model="userData.firstName">
                        <input
                                type="text"
                                id="lastName"
                                class="form-control"
                                v-model="userData.lastName">
                    </div>
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="isSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ userData.name}}</p>
                        <p>Mail: {{ userData.email }}</p>
                        <p>Password: {{ userData.password }}</p>
                        <p>Store in Database?: {{ storeData}}</p>
                        <p>Full Name: {{userData.firstName + " "  + userData.lastName }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                userData: {
                    name: '',
                    email: '',
                    password: '',
                    firstName: 'First',
                    lastName: 'Last'

                },
                storeData: 'Yes',
                isSubmitted: false
            }

        },
        methods: {
            submitted() {
                this.isSubmitted = true
            }
        },
    }
</script>

<style>
</style>
