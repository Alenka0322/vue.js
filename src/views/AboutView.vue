<template>
    <v-app>
   <v-card width="400" class="mx-auto mt-5">
    <v-card-title>
     <h1>Login</h1>
    </v-card-title>

    <v-card-text>
    <v-form>
    <v-text-field label="Username"
    prepend-icon="mdi-account-circle"
    />
    <v-text-field
     :type="showPassword ? 'text' : 'password'"
     label="Password"
     prepend-icon="mdi-lock"
     :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
     @click:append="showPassword = !showPassword"
    />
    </v-form>
    </v-card-text>
    <v-divider></v-divider>
    <v-card-action class="btn pa-3" >
        <v-btn  color="info">Registr</v-btn>
        <v-spacer></v-spacer>
        <v-btn color="teal">Login</v-btn>
    </v-card-action>

   </v-card>
    </v-app>
</template>


<script>
export default {
    name: 'About',
    data: () => ({
     showPassword: false
    }),
}
</script>


<style>
.btn {
    display: flex;
    
}

</style>