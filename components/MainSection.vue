<template>
  <div class="main">
    <img src="@/assets/images/head.jpg" alt="theater-image" />
    <div class="text-container">
      <div class="text">
        <p class="mini-text">now streamaing</p>
        <h1><span>now</span> streamaing</h1>
        <a href="#movies">view movies</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "main-section",
};
</script>

<style lang="scss" scoped>
.main {
  height: 100vh;
  width: 100vw;
  overflow: hidden;
  position: relative;
  &::after {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    background-color: #0c0c0c7c;
  }
  img {
    width: 100%;
    height: 100%;
  }
  .text-container {
    z-index: 999;
    padding: 0 100px;
    position: absolute;
    top: 0;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    .text {
      width: 90%;
      margin: 0 auto;
      .mini-text {
        font-size: 1.2rem;
        width: 100%;
        color: red;
        text-transform: uppercase;
        @media (max-width: 750px) {
          font-size: 1rem;
        }
      }
      h1 {
        font-size: 3rem;
        color: #fff;
        text-transform: capitalize;
        font-weight: 200;
        @media (max-width: 750px) {
          font-size: 2rem;
        }
        span {
          font-weight: 900;
        }
      }
      a {
        padding: 10px 40px;
        background-color: red;
        color: #fff;
        font-size: 1.2rem;
        border: none;
        border-radius: 5px;
        display: block;
        margin: 10px 0;
        transition: all ease-in 0.2s;
        text-decoration: none;
width: fit-content;
        @media (max-width: 750px) {
          font-size: 1rem;
          padding: 10px 20px;
        }
      }
    }
  }
}
</style>
