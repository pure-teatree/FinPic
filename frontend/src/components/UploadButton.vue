<template>
  <div
    id="signUpButton"
    class="btndiv"
    v-if="token != null && token.length != 0 && token != 'undefined'"
  >
    <button type="button" class="button" v-on:click="UploadPageLink">Upload</button>
  </div>
</template>

<script>
const storage = window.sessionStorage;

export default {
  name: "UploadButton",
  methods: {
    UploadPageLink: function () {
      this.$router.push("/uploadpage");
      this.$router.go("/");
    },
  },
  data: function () {
    return {
      token: storage.getItem("jwt-auth-token"),
    };
  },
};
</script>
<style>
.btndiv {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.button {
  width: 100px;
  height: 40px;
  font-family: "NanumSquare", sans-serif;
  font-size: 15px;
  text-transform: uppercase;
  letter-spacing: 2.5px;
  font-weight: 500;
  color: white;
  background-color: #323232;
  border: none;
  border-radius: 10px;
  box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease 0s;
  cursor: pointer;
  outline: none;
}

.button:hover {
  background-color: #fff;
  box-shadow: 0px 15px 20px rgba(103, 63, 191, 0.4);
  color: #323232;
  transform: translateY(-7px);
}
@font-face {
  font-family: "NanumSquare";
  src: url("./../assets/NanumSquare.ttf");
}
</style>