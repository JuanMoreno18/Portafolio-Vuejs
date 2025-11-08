<template>
  <div class="fondo-lava">
    <div class="gradient-bg">
      <svg xmlns="http://www.w3.org/2000/svg">
        <defs>
          <filter id="goo">
            <feGaussianBlur in="SourceGraphic" stdDeviation="10" result="blur" />
            <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 18 -8" result="goo" />
            <feBlend in="SourceGraphic" in2="goo" />
          </filter>
        </defs>
      </svg>
      <div class="gradients-container">
        <div class="g1"></div>
        <div class="g2"></div>
        <div class="g3"></div>
        <div class="g4"></div>
        <div class="g5"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FondoLava",
};
</script>

<style scoped>
.fondo-lava {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  z-index: 0;
  border-radius: 40px;
}

.gradient-bg {
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
  background: linear-gradient(40deg, #0a1929, #1a2332, #0f1b2d);
}

svg {
  display: none;
}

.gradients-container {
  filter: url(#goo) blur(40px);
  width: 100%;
  height: 100%;
}

.g1, .g2, .g3, .g4, .g5 {
  position: absolute;
  mix-blend-mode: hard-light;
  border-radius: 50%;
  filter: blur(60px);
}

.g1 {
  background: radial-gradient(circle at center, rgba(255, 68, 68, 0.8) 0%, rgba(255, 68, 68, 0) 50%);
  width: 80%;
  height: 80%;
  top: -40%;
  left: -20%;
  animation: moveVertical 30s ease infinite;
}

.g2 {
  background: radial-gradient(circle at center, rgba(68, 138, 255, 0.8) 0%, rgba(68, 138, 255, 0) 50%);
  width: 70%;
  height: 70%;
  top: -30%;
  right: -20%;
  animation: moveInCircle 20s reverse infinite;
}

.g3 {
  background: radial-gradient(circle at center, rgba(255, 136, 0, 0.8) 0%, rgba(255, 136, 0, 0) 50%);
  width: 90%;
  height: 90%;
  top: 10%;
  left: -30%;
  animation: moveInCircle 40s linear infinite;
}

.g4 {
  background: radial-gradient(circle at center, rgba(187, 68, 255, 0.8) 0%, rgba(187, 68, 255, 0) 50%);
  width: 60%;
  height: 60%;
  bottom: -30%;
  right: -10%;
  animation: moveHorizontal 40s ease infinite;
}

.g5 {
  background: radial-gradient(circle at center, rgba(0, 255, 136, 0.8) 0%, rgba(0, 255, 136, 0) 50%);
  width: 80%;
  height: 80%;
  bottom: -40%;
  left: 10%;
  animation: moveVertical 25s ease infinite;
}

@keyframes moveInCircle {
  0% {
    transform: rotate(0deg) translateX(100px) rotate(0deg);
  }
  100% {
    transform: rotate(360deg) translateX(100px) rotate(-360deg);
  }
}

@keyframes moveVertical {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(100px);
  }
  100% {
    transform: translateY(0px);
  }
}

@keyframes moveHorizontal {
  0% {
    transform: translateX(0px);
  }
  50% {
    transform: translateX(-100px);
  }
  100% {
    transform: translateX(0px);
  }
}

/* === Ajustes responsive === */
@media (max-width: 768px) {
  .fondo-lava {
    border-radius: 20px;
  }

  .g1, .g2, .g3, .g4, .g5 {
    filter: blur(40px);
  }
}

@media (max-width: 480px) {
  .fondo-lava {
    border-radius: 10px;
  }

  .g1, .g2, .g3, .g4, .g5 {
    filter: blur(30px);
  }
}
</style>