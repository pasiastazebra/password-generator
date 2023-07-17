<template>
    <div class="footer">
      <img src="@/assets/git.svg" alt="GitHub Logo" class="footer-image">
      <a href="https://github.com/pasiastazebra" class="footer-text">/pasiastazebra 📎</a>
    </div>
</template>
  
  <script> 
  export default {
    name: 'SiteFooter',
  };
  </script>
  
  <style scoped lang="scss">
  .footer {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 0%;

    background: #159957;

    &-image{
      width: 30px;
      height: 30px;
      display: block;
      margin: 1px;
    }

    &-text{
      display: inline-block;
      align-self: flex-end;
      font-size: 25px;
    }
  }
  </style>