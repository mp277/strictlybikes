<template>
    <Page>
        <FlexboxLayout class="page">
            <StackLayout class="form">
                <Image class="logo" src="https://cdn.pixabay.com/photo/2019/04/02/21/47/cyclist-4098989_960_720.png" />
                <Label class="header" text="Strictly Bikes" />

                <Button text='Login'
                    @tap="onLoginTap" class="btn btn-primary m-t-20" />
            </StackLayout>

        </FlexboxLayout>
    </Page>
</template>




<script>
  import { tnsOauthLogin } from '../../auth/auth-service';
  export default {
    methods: {
      onLoginTap() {
        console.log("login clicked");
        tnsOauthLogin('google', () => {
          this.$goto('Home');
        });
      }
    },
  }
</script>

<style lang="scss" scoped>
    .page {
        align-items: center;
        flex-direction: column;
    }

    .form {
        margin-left: 30;
        margin-right: 30;
        flex-grow: 2;
        vertical-align: middle;
    }

    .logo {
        margin-bottom: 12;
        height: 200;
        font-weight: bold;
    }

    .header {
        horizontal-align: center;
        font-size: 40;
        font-weight: 600;
        margin-bottom: 70;
        text-align: center;
        color: #5EB0E5;
    }

    .input-field {
        margin-bottom: 25;
    }

    .input {
        font-size: 18;
        placeholder-color: #A8A8A8;
    }

    .input-field .input {
        font-size: 54;
    }

    .btn-primary {
        height: 50;
        margin: 30 5 15 5;
        background-color: #5EB0E5;
        border-radius: 5;
        font-size: 20;
        font-weight: 600;
    }

    .login-label {
        horizontal-align: center;
        color: #A8A8A8;
        font-size: 16;
    }

    .sign-up-label {
        margin-bottom: 20;
    }

    .bold {
        color: #000000;
    }
</style>