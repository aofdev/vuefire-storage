<template>
<div class="hello">

  <progress value="0" max="100" id="uploader"></progress>
  <input accept="image/*" type="file" value="upload" @change="fileBtn(file, $event)">
</div>
 
 
 

</template>

<script>
  import Firebase from 'firebase'
    const config = {
   //firebase console
    }
    const app = Firebase.initializeApp(config);


export default {
  name: 'hello',
  data () {
    return {
     
    }
  },
  methods:{
    fileBtn:function(file, e){
        e.preventDefault();
      const uploader = document.getElementById('uploader');
      //get file
      let getFile = e.target.files[0];
      //set storage ref
      let storageRef = Firebase.storage().ref('test/'+getFile.name);
      //upload file
      let task = storageRef.put(getFile);
      task.on('state_changed',
       function progress(snapshot){
        let percentage = (snapshot.bytesTransferred / snapshot.totalBytes) *100;
        uploader.value = percentage;
      },
      function error(err){

      },
      function complete(){

      }
      );
    }
  }
}
</script>



