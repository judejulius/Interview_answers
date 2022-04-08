<template>
  <div>
    <div class="number" :id="'number'+number" v-for="number in n()" :key="number" @mouseover="hov(number)" @mouseout="reset">
      {{number}}
    </div>
  </div>
</template>

<script>
export default {
  data()
  {
    return {
      limit: this.$parent.limit,
      numbers: []
    }
  },
  watch: {
    ['$parent.limit'](newLimit)
    {
      this.limit = newLimit;
    }
  },
  methods: {
    //Naming conventions need to be better
    n()
    {
      let numbers = [];
      for(var i = 0; i < this.limit; i++)
      {
        // numbers = [...numbers, i];
        //instead of using the line above i used numbers.push
        numbers.push(i) 
      }
      return numbers.sort(() => Math.random() - 0.5);
    },
    //Naming conventions need to be better
    hov(number)
    {
      //DOM we dont use in vue
      const nums = document.querySelectorAll('.number');
    //maybe use a v model
      for(let i = 0; i < nums.length; i++)
      {
        const num = nums[i].textContent.trim();
        if(number % num === 0)
        {
          nums[i].classList.add('active')
          console.log('divisor', num)
        }
      }
    },
    reset()
    {
      const nums = document.querySelectorAll('.number');
      nums.forEach(num => num.classList.remove('active'))
    }
  }
}
</script>

<style scoped>
	.number {
		display: inline-block;
		padding: 5px;
		background-color: lightgrey;
		margin: 5px;
	}

	.active {
		background-color: red;
	}
  div{
    font-size: 2rem;
    font-family: sans-serif;
    border-radius: 12px;
  }
  input{
    height: 30px;
  }

</style>
