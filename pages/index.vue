<template>
  <div>
    <main class="flex align-items-center justify-content-center">
        <section id="mobile" class="flex">
        </section>
        <section id="auth" class="flex direction-column">
            <div class="panel login flex direction-column">
                <h1 title="Instagram" class="flex justify-content-center">
                    <img src="/img/instagram-logo.png" alt="Instagram logo" title="Instagram logo" />
                </h1>
                <form>
                    <label for="email" class="sr-only">Phone number, username, or email</label>
                    <input name="email" v-model="form.email" placeholder="Phone number, username, or email" />

                    <label for="password" class="sr-only">Password</label>
                    <input name="password" v-model="form.password" type="password" placeholder="Password" />

                    <button type="button" @click="onSubmit">Log in</button>
                </form>
                <div class="flex separator align-items-center">
                    <span></span>
                    <div class="or">OR</div>
                    <span></span>
                </div>
                <div class="login-with-fb flex direction-column align-items-center">
                    <div>
                        <img />
                        <a>Continue with Facebook</a>
                    </div>
                    <a href="#">Forgot password?</a>
                </div>
            </div>
            <div class="panel register flex justify-content-center">
                <p>Don't have an account?</p>
                <a href="#">Register</a>
            </div>
            <div class="app-download flex direction-column align-items-center">
                <p>Get the app.</p>
                <div class="flex justify-content-center">
                    <img src="/img/apple-button.png"      alt="Imagem com a logo da Apple Store" title="Imagem com a logo da Apple Store" />
                    <img src="/img/googleplay-button.png" alt="Imagem com a logo da Google Play" title="Imagem com a logo da Google Play" />
                </div>
            </div>
        </section>
    </main>
    <footer>
        <ul class="flex flex-wrap justify-content-center" style="font-size: 12px;">
            <li v-for="link in footer_links" :key="link"><a href="#">{{link}}</a></li>
        </ul>
        <p class="copyright" style="font-size: 14px;">?? 2022 Instagram from Meta</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      form: {
        email: null,
        password: null
      },
      footer_links: ["Meta","About","Blog","Jobs","Help","API","Privacy","Terms","Top Accounts","Hashtags","Locations","Instagram Lite","Contact Uploading & Non-Users"
      ]
    }
  },
  methods: {
    onSubmit() {
      console.log(this.form)
    }
  }
}
</script>

<style>
  * {
    border: none;
    box-sizing: border-box;
    font-family: Arial, Helvetica, sans-serif;
    margin: 0;
    padding: 0;
}

body {
    background-color: #fafafa;
    height: 100vh;
}

main {
    height: 100vh;
    margin: auto;
    max-width: 935px;
}

a { text-decoration: none; }
h1 { margin: 20px 0; }
ul { list-style: none; }

/**
 * Flex rules
 */

.flex {
    display: -webkit-box;
    display: -moz-box;
    display: -webkit-flex;
    display: -ms-flexbox;
    display: flex;
}

.direction-column {
    -webkit-box-direction: normal;
    -webkit-box-orient: vertical;
    -moz-box-direction: normal;
    -moz-box-orient: vertical;
    -webkit-flex-direction: column;
    -ms-flex-direction: column;
    flex-direction: column;
}

.justify-content-center {
    -webkit-box-pack: center;
    -moz-box-pack: center;
    -ms-flex-pack: center;
    -webkit-justify-content: center;
    justify-content: center;
}

.align-items-center {
    -webkit-box-align: center;
    -moz-box-align: center;
    -ms-flex-align: center;
    -webkit-align-items: center;
    align-items: center;
}

.flex-wrap {
    -webkit-flex-wrap: wrap;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
}

/**
 *
 */

.panel {
    background-color: white;
    border: 1px solid #dbdbdb;
    margin-bottom: 10px;
    padding: 10px;
}

#auth { max-width: 350px; }
#mobile { max-width: 454px; }

#mobile img {
    height: 618px;
}

/**
 * Login section
 */
.login-with-fb,
form { width: 100%; }

.register,
form { padding: 30px 20px; }

.login-with-fb { padding: 30px 20px 20px 20px; }

form .sr-only { display: none; }

form input {
    background-color: #fafafa;
    border: 1px solid #dbdbdb;
    border-radius: 3px;
    color: #808080;
    margin-bottom: 8px;
    padding: 10px 10px;
    width: 100%;
}

form input::placeholder {
    color: #808080;
}

form input:focus {
    border: 1px solid #808080;
    outline: none;
}

form button {
    background-color: #0095f6;
    border-radius: 5px;
    color: #fff;
    font-weight: bold;
    height: 35px;
    margin-top: 10px;
    width: 100%;
}

/**
 * Separator login form from login with fb
 */
.separator span {
    background-color: #dbdbdb;
    height: 1px;
    width: calc(100% - 10px);
}

.separator .or {
    color: #808080;
    font-weight: bold;
}

.separator { padding: 0 20px; }
.separator span:first-child { margin-right: 10px;}
.separator span:last-child { margin-left: 10px;}

/**
 * Login with fb section
 */
.login-with-fb a { 
    color: #385185; 
}

.login-with-fb > a { font-size: 12px; }
.login-with-fb div a { font-weight: bold; }
.login-with-fb div { margin-bottom: 15px; }

/**
 * Register section
 */
.register * { font-size: 14px; }
.register a { 
    color: #0095f6;
    font-weight: bold;
}

.register p { margin-right: 5px; }

/**
 * App download
 */
.app-download { padding: 15px; }
.app-download p { padding: 10px 0; }
.app-download img { 
    height: 40px; 
    margin: 0 5px;
}

/**
 * Footer
 */
footer {
    margin: 0 auto 30px auto;
    max-width: 935px;
}
footer ul { margin-bottom: 20px; }
footer ul li { margin: 0 10px 10px; } 
footer ul li a { color: #385185; }
footer .copyright { color: #808080; }
footer ul li a,
footer .copyright { 
    font-weight: bold;
    text-align: center;
    text-transform: uppercase;
 }


/**
 * Media queries
 */

@media screen and (max-width: 767px) {
    main { margin: 30px auto 50px auto; }
    footer .copyright,
    footer ul li a { font-size: 13px; }
}
</style>
