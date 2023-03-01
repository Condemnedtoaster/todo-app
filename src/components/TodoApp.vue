<template>
  <div class="container">
   <h2 class="text-center mt-5">My vue todo app</h2>

<div class="d-flex">
  <input v-model="task" type="text" placeholder="Enter text" class="form-control">
<button @click ="submitTask" class="btn btn-warning rounded-0">
  Submit

</button>
</div>


<table class="table table-bordered mt-5">
  <thead>
    <tr>
      <th scope="col">task  #</th>
      <th scope="col">status</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(task, index) in tasks" :key="index">
      <th>{{task.name}}</th>
      <td>{{task.status}}</td>
      
    </tr>
    
  </tbody>
</table>






  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
data(){
  return{
    task:'',
    tasks: [
      


    ]


  }

},

methods:{ 
 
 

  reverseString(str) {
    // Step 1. Create an empty string that will host the new created string
    var newString = "";
 
    // Step 2. Create the FOR loop
    /* The starting point of the loop will be (str.length - 1) which corresponds to the 
       last character of the string, "o"
       As long as i is greater than or equals 0, the loop will go on
       We decrement i after each iteration */
    for (var i = str.length - 1; i >= 0; i--) { 
        newString += str[i]; // or newString = newString + str[i];
    }
    /* Here hello's length equals 5
        For each iteration: i = str.length - 1 and newString = newString + str[i]
        First iteration:    i = 5 - 1 = 4,         newString = "" + "o" = "o"
        Second iteration:   i = 4 - 1 = 3,         newString = "o" + "l" = "ol"
        Third iteration:    i = 3 - 1 = 2,         newString = "ol" + "l" = "oll"
        Fourth iteration:   i = 2 - 1 = 1,         newString = "oll" + "e" = "olle"
        Fifth iteration:    i = 1 - 1 = 0,         newString = "olle" + "h" = "olleh"
    End of the FOR Loop*/
 
    // Step 3. Return the reversed string
    return newString; // "olleh"
},

FirstAndLast(str)
{
 
    // Create an equivalent string
    // of the given string
    var ch = str.split('');
    for (var i = 0; i < ch.length; i++)
    {
 
        // k stores index of first character
        // and i is going to store index of last
        // character.
        var k = i;
        while (i < ch.length && ch[i] != ' ')
            i++;
 
        // Check if the character is a small letter
        // If yes, then Capitalise
        ch[k] = String.fromCharCode(ch[k] >= 'a' &&
        ch[k] <= 'z' ? (ch[k].charCodeAt(0) - 32)
                     : ch[k].charCodeAt(0));
        ch[i - 1] = String.fromCharCode(ch[i - 1] >= 'a'
        && ch[i - 1] <= 'z'? (ch[i - 1].charCodeAt(0) - 32)
                            : ch[i - 1].charCodeAt(0));
    }
 
    return ch.join('');
},
capitalizeLast(strr)
{
 
  var str = strr;
      
      //get size of the string 
      var size = strr.length;
      
      //get last character and convert it to upper case
      var last = str.substring(size-1,size);
      var lastinUpper = last.toUpperCase();
      
      //get first character and convert it to lower case
      var first = str.substring(0,1);
      var firstinLower = first.toLowerCase();
      
      //get middle parts of the word, except first and last character
      var middle = str.substring(1,size-1);
      
      //combine everything and get the final string
      var result = firstinLower+middle+lastinUpper;
      
      //print result
      return result;
},



  
  submitTask()
  
  {

    if(this.task.length === 0) return;
    this.tasks.push({
      name: this.task,
      status: "checked"
      
    },
    {
      name: this.task.toUpperCase(this.task.name),
      status: "checked"
    },
    {
      name: this.task.toLowerCase(this.task.name),
      status: "checked"

    },
    {
      name: this.task.charAt(0).toUpperCase(this.task.name)+this.task.slice(1),
      status: "checked" 

    },
    {
      


     
      name: this.capitalizeLast(this.task),
      status: "checked"


    },
    {
      
      
      name: this.reverseString(this.task),
      status: "checked"




    }
    


   // {
     // name: this.task.reverseString(this.task.name)
    //}
    
    
    )




  }

}



}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
