<template>
  <div class="container">
    <div class="row">
      <div class="col-sm-12">
        <nav-header @pageWasChanged="currentPage = $event"></nav-header>
        <keep-alive>
        <component :is="currentPage"></component>
        </keep-alive>
        <cc-footer>
          <p class="text-center">&copy; Creative Cards</p>
        <nav>
          <ul class="nav justify-content-center">
            <li class="nav-item"><a class="nav-link">Home</a></li>
            <li class="nav-item"><a class="nav-link">About Us</a></li>  
            <li class="nav-item"><a class="nav-link">Contact Us</a></li> 
          </ul>
        </nav>
          </cc-footer>
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import CardFront from './components/card/CardFront.vue'
import CardInsideLeft from './components/card/CardInsideLeft.vue'
import CardInsideRight from './components/card/CardInsideRight.vue'
import CardBack from './components/card/CardBack.vue'
import Footer from './components/Footer.vue'
import FirebaseConfig from './firebaseConfig.js'

export default {
  data: function() {
    return {
      currentPage: 'cardFront'
    }
  },
  components: {
    navHeader: Header,
    cardFront: CardFront,
    cardInsideLeft: CardInsideLeft,
    cardInsideRight: CardInsideRight,
    cardBack: CardBack,
    ccFooter: Footer
  }
}
</script>

<style>
  body {
    font-family: Verdana, Geneva, sans-serif;
    color: #333;
  }

  h1 {
    margin-top: 10px;
  }

  a {
    cursor: pointer;
  }

      p {
        font-family: 'Tangerine', cursive;
        font-size: 42px;
        line-height: 42px;
        text-shadow: 2px 2px 2px #aaa;
        color: #4d4d4d;
        margin: 5px 0;
        border: 1px dotted grey;
        white-space: pre-line;
        overflow: hidden;
    }

    .bold {
        font-weight: bold;       
    }

    .italic {
        font-style: italic;
    }

    form {
        position: absolute;
        border: 1px dotted grey;
        margin-top: 10px;
        margin-bottom: 5px;
        padding-bottom: 5px;
    }

    select {
        height: 40%;
    }

    .fade-enter, .fade-leave-to {
        opacity: 0;
    } 

    .fade-enter-active, .fade-leave-active {
        transition: opacity .5s;
    }
</style>
