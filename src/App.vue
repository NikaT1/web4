<template>
  <div id="app">
    <notifications class="notify" group="error" position="top right" max="6" close-on-click width="30%"/>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
}
</script>
<style>

* { padding: 0; margin: 0; }

html, body {
  background-color: #ffffff;
  width: 100%;
  height: 100%;
  font-family: Inter, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell,
  "Fira Sans", "Droid Sans", Helvetica, Arial, sans-serif;
}

.main-background {
  background: linear-gradient(rgba(234, 230, 230, 0.15), rgba(252, 251, 251, 0.15)),
  url("assets/background.jpg") center/cover;
}

.background {
  background: rgba(255, 255, 255, 0.7);
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  border-radius: 5px;
}

#app {
  width: 100%;
  height: 100%;
}

input[type="text"] {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
  margin: 0;
}

input:-webkit-autofill,
input:-webkit-autofill:hover,
input:-webkit-autofill:focus,
textarea:-webkit-autofill,
textarea:-webkit-autofill:hover,
textarea:-webkit-autofill:focus,
select:-webkit-autofill,
select:-webkit-autofill:hover,
select:-webkit-autofill:focus {
  border: 1px solid #bdbdbd;
  -webkit-text-fill-color: #212529;
  -webkit-box-shadow: 0 0 0px 1000px #fff inset;
  transition: background-color 5000s ease-in-out 0s;
}

.input-field {
  display: block;
  width: 100%;
  height: calc(2.25em + 2px);
  padding: 0.375em 0.75em 0.375em 0.75em;
  font-family: inherit;
  font-size: 1em;
  font-weight: 400;
  line-height: 1.5;
  color: #212529;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #bdbdbd;
  border-radius: 0.25rem;
  transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
}

input::placeholder {
  color: #212529;
  opacity: 0.4;
}

.notify {
  font-family: New Century Schoolbook, TeX Gyre Schola, serif;
  font-size: 30px;
}

p {
  color: #2b2b2b;
}

a {
  text-decoration: none
}

a:link {
  color: #ababab;
}
a:visited {
  color: #ababab;
}
a:hover {
  color: #fdfdfd;
}
a:active {
  color: #7c7c7c;
}

::-webkit-scrollbar {
  width: 10px;
}

::-webkit-scrollbar-track {
  box-shadow: inset 0 0 6px rgba(86, 85, 86, 0.49);
}

::-webkit-scrollbar-thumb {
  box-shadow: inset 0 0 6px rgba(101, 98, 102, 0.49);
}

</style>