function opensmiley(){
        document.getElementById('overlay').style.display='block';
        document.getElementById('emoji_modal').style.display='block';
}
function emojiesinp(elem){
    var qwefgfghgrtyui = elem.innerHTML;
    var ertyhjgfgyhjhbgvfghj = document.getElementById('contact_message_value').value;
     document.getElementById('contact_message_value').value =ertyhjgfgyhjhbgvfghj+qwefgfghgrtyui;
}
function closesmiley(){
       document.getElementById('emoji_modal').classList.add("close_emoji_modal");
        document.getElementById('overlay').style.display='none';
   setTimeout(function(){document.getElementById('emoji_modal').classList.remove("close_emoji_modal");
    document.getElementById('sent_modal').classList.remove("close_emoji_modal");
    document.getElementById('emoji_modal').style.display='none';
    document.getElementById('sent_modal').style.display='none';
                        }, 300);
}
function closesent(){
       document.getElementById('sent_modal').classList.add("close_emoji_modal");
        document.getElementById('overlay').style.display='none';
   setTimeout(function(){document.getElementById('sent_modal').classList.remove("close_emoji_modal");
    document.getElementById('sent_modal').style.display='none';}, 300);
}
function removered(thisy){
    if(thisy == "contact"){
       document.getElementById("contact").style.border = "none";  
       }else{
         if(thisy == "message"){
       document.getElementById("contact_message_value").style.border = "none"; 
       }else{
        if(thisy == "name"){
             document.getElementById("contact_name").style.border = "none"; 
       }   
       }  
       }  
}
function addred(){
    document.getElementById("contact").style.border = "1px solid red";  
           document.getElementById("contact_name").style.border = "1px solid red";  
           document.getElementById("contact_message_value").style.border = "1px solid red";
}
function addyed(thigyhsy){
        var name = document.getElementById("contact_name").value;  
    var contact = document.getElementById("contact").value;  
         var message = document.getElementById("contact_message_value").value; 
    if(thigyhsy == "contact"){
             if (contact.length == 0){
                 document.getElementById("contact").style.border = "1px solid red";
        }else{
            var inputcon = $('#contact');
         if($(inputcon).val().trim() == ''){
             document.getElementById("contact").style.border = "1px solid red";
         }}
       }else{
         if(thigyhsy == "message"){
        if (message.length == 0){
                 document.getElementById("contact_message_value").style.border = "1px solid red";
        }else{
            var inputconmess = $('#contact_message_value');
         if($(inputconmess).val().trim() == ''){
             document.getElementById("contact_message_value").style.border = "1px solid red";
         }}
       }else{
        if(thigyhsy == "name"){
             if (name.length == 0){
                 document.getElementById("contact_name").style.border = "1px solid red";
        }else{
            var inputconname = $('#contact_name');
         if($(inputconname).val().trim() == ''){
             document.getElementById("contact_name").style.border = "1px solid red";
         }} 
       }   
       }  
       }  
}
function validate_contact(){
    var name = document.getElementById("contact_name").value;  
    var contact = document.getElementById("contact").value;  
var message = document.getElementById("contact_message_value").value; 
             if (name.length !== 0){
             if (contact.length !== 0){
             if (message.length !== 0){
        var input = $('.vli');
         if($(input).val().trim() !== ''){
             if (window.XMLHttpRequest) {var usercheck = new XMLHttpRequest();} 
    else if (window.ActiveXObject) {var usercheck = new ActiveXObject("Microsoft.XMLHTTP");}  
    usercheck.open("POST", "./receive.php", true);
usercheck.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
usercheck.send("name="+name+"&contact="+contact+"&message="+message);
usercheck.onreadystatechange = function() {
  if(usercheck.readyState == 4 && this.status == 200) {
    document.getElementById('overlay').style.display='block';
        document.getElementById('sent_modal').style.display='block';
     document.getElementById("contact").value = "";  
    document.getElementById("contact_name").value = "";  
    document.getElementById("contact_message_value").value = ""; 
    }
}; 
             return false;
         }else{
           addred();
             return false;
         }
             }else{
           addyed('message');
                 return false;
         }}else{
           addyed('contact');
             return false;
         }}else{
          addyed('name');
             return false;
         }
    return false;
} 
$(document).ready(function(){
		$('.hover').hover(function(){
			$(this).addClass('flip');
		},function(){
			$(this).removeClass('flip');
		});
	});
