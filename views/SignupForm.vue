<template>
<h1 style="box-shadow: inset 0 -6px 0 black; color:white;">CONTACT ME</h1>
<div class="SignupForm"></div>

  <form @submit.prevent="handleSubmit">
<!-- The form that has input boxes for email, password and roles -->
      <label>Email:</label>
      <input type="email" required v-model="email">
        <label>Password:</label>
      <input type="password" required v-model="password">
      <div v-if="passwordError" class="error">{{ passwordError }}</div>
      <label>Role:</label>
        <select v-model="role">
            <option value="developer">Web Developer</option>
            <option value="designer">Web Designer</option>
            <option value="recruiter">Recruiter</option>
        </select>

<!-- The terms & conditions section with a checkbox -->
        <div class="terms">
            <input type="checkbox" v-model="terms" required>
            <label>Accept terms and conditions</label>
        </div>

<!-- Submission button to create account -->
        <div class="submit">
            <button class="button"><h1>Submit</h1></button>
        </div>
  </form>

</template>

<script>
// This section covers my Javascript exports with data that is binded to my template specified properties in order to return the needed data and perform method functions indicated. 
export default {
    name: 'SignupForm',
    data() {
        return {
            email: '',
            password: '',
            role: '',
            terms: false,
            passwordError: ''
        }
    },
    methods: {
        handleSubmit() {
            // validate password
            this.passwordError = this.password.length > 5 ? 
            '' : 'Password must be at least 6 characters long'
        }
    }
}
</script>

<style>
/* This is my styling for the whole Signup Form */
.SignupForm{
    background-color: burlywood;
}
    form {
    max-width: 420px;
    margin: 30px auto;
    background: whitesmoke;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
    }
    label {
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
    }
    input, select {
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
    }
    input[type="checkbox"] {
        display: inline-block;
        width: 16px;
        margin: 0 10px 0 0;
        position: relative;
        top: 2px;
    }
    .pill {
        display: inline-block;
        margin: 20px 10px 0 0;
        padding: 6px 12px;
        background: #eee;
        border-radius: 20px;
        font-size: 12px;
        letter-spacing: 1px;
        font-weight: bold;
        color: #777;
        cursor: pointer;
    }
    .button {
        background: #0b6dff;
        border: 0;
        padding: 10px 20px;
        margin-top: 20px;
        color: white;
        border-radius: 20px;
    }
    .submit {
        text-align: center;
    }
    
    .error {
        color: #ff0062;
        margin-top: 10px;
        font-size: 0.8em;
        font-weight: bold;
    }
</style>