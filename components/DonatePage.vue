<!-- https://codepen.io/rosswaycaster/pen/YPQzap -->
<template>

<div class="donation-container">      
     <div class="donation-box">
        <div class="title">Donation Information</div>    
        <div class="fields">
            <input type="text" id="firstName" placeholder="First Name"/>
            <input type="text" id="lastName" placeholder="Last Name"/> 
            <input type="text" id="email" placeholder="Email"/>
        </div>
        <div class="amount">
            <div class="button">$30</div>
            <div class="button">$50</div>
            <div class="button">$100</div>
            <div class="button">
                $<input type="text" class="set-amount" placeholder=""/>
            </div>
        </div>
        <div class="checkboxes">
            <input type="checkbox" id="receipt" class="checkbox"/>
            <label for="receipt">Email Me A Receipt</label>
            <br/>
            <input type="checkbox" id="anon" class="checkbox" />
            <label for="anon">Give Anonymously</label>
            <br />
            <input type="checkbox" id="list" class="checkbox" />
            <label for="list">Add Me To Email List</label>
        </div>    
        <div class="donate-button">
            <i class="fa fa-credit-card"></i> 
            Donate Now
        </div>
    </div>
</div>    

</template>
<script>
export default{
    data: function() {
        return {
            
        }
    }
}
</script>
<style>
.donation-container {
    /*position: relative;*/
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
    font-size: 12px;
    height: 100%;
    text-transform: uppercase;
    margin-top: 30px;
}

.donation-box {
    /*position: absolute;*/
    /*top: 0px;*/
    /*right: 0px;*/
    height: 400px;
    width: 100%;
    background-color: white;
    border-top-left-radius: 4px;
    border-top-right-radius: 4px;
    position: relative;
    margin-left: auto;
    margin-right: auto;
    
    -webkit-transition: all 0.15s ease-out;
    -moz-transition: all 0.15s ease-out;
    -o-transition: all 0.15s ease-out;
    transition: all 0.15s ease-out;
}

.donation-box .title {
    background-color: black;
    width: 100%;
    border-top-left-radius: 4px;
    border-top-right-radius: 4px;
    color: white;
    text-align: center;
    padding-top: 12px;
    padding-bottom: 12px;
    font-size: 15px;
}

.donation-box .donate-button {
    background-color: black;
    width: 100%;
    color: white;
    text-align: center;
    padding-top: 12px;
    padding-bottom: 12px;
    font-size: 18px;
    bottom: 0px;
    position: absolute;
    cursor: pointer;
    font-weight: 800;
}

.donation-box .fields {
    width: 59%;
    display: block;
    position: absolute;
    top: 60px;
    left: 15px;
}

.donation-box .fields input {
    width: 90%;
    font-size: 17px;
    padding: 10px;
    border-radius: 4px;
    border-width: 2px;
    border-color: black;
    color: #5C5C5C;
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
    margin-bottom: 10px;
    -webkit-font-smoothing: antialiased;
    outline: none;
}

::-webkit-input-placeholder {
   color: #cdcdcd;
   font-size: 15px;
}

:-moz-placeholder { /* Firefox 18- */
   color: #cdcdcd;
   font-size: 15px;
}

::-moz-placeholder {  /* Firefox 19+ */
   color: #cdcdcd;
   font-size: 15px; 
}

:-ms-input-placeholder {  
   color: #cdcdcd;
   font-size: 15px;
}

.donation-box .amount {
    width: 30%;
    display: block;
    position: absolute;
    top: 60px;
    right: 15px;
}

.donation-box .amount .button {
    width: 100%;
    background-color: gray;
    margin-bottom: 10px;
    text-align: center;
    color: white;
    padding: 15px 0px 15px 0px;
    border-radius: 4px;
    font-size: 20px;
    cursor: pointer;
    
    -webkit-transition: 400ms background-color;
    -moz-transition: 800ms opacity, 800ms right;
    -ms-transition: 800ms opacity, 800ms right;
    -o-transition: 800ms opacity, 800ms right;
    transition: 200ms background-color;
}

.donation-box .amount .button:hover {
    background-color: #393939;
}

.donation-box .amount .button.selected {
    background-color: #393939;
}

.donation-box .amount .button input {
    min-width: 34px;
    font-size: 20px;
    font-weight: 500;
    border: none;
    background-color: transparent;
    color: white;
    font-family: Montserrat, sans-serif;
    font-size: 20px;
    font-stretch: normal;
    font-style: normal;
    font-variant: normal;
    font-weight: 500;
    border-bottom: 2px dashed white;
    -webkit-font-smoothing: antialiased;
    
    -webkit-transition: all 0.15s ease-out;
    -moz-transition: all 0.15s ease-out;
    -o-transition: all 0.15s ease-out;
    transition: all 0.15s ease-out;
}

.set-amount {
    max-width: 96px;
}

.checkboxes {
    position: absolute;
    top: 242px;
    left: 13px;
}

.checkboxes label {
    position: relative;
    top: -8px;
    font-size: 13px;
    color: gray;
}

.checkbox {
    -webkit-appearance: none;
    background-color: white;
    border: 1px solid black;
    padding: 9px;
    border-radius: 3px;
    display: inline-block;
    position: relative;
  outline: none;
    
    -webkit-transition: all 0.15s ease-out;
    -moz-transition: all 0.15s ease-out;
    -o-transition: all 0.15s ease-out;
    transition: all 0.15s ease-out;
}

.checkbox:active, .checkbox:checked:active {
    
}

.checkbox:checked {
    background-color: black;
    border: 1px solid black;
    color: white;
}

.checkbox:checked:after {
    content: '\2714';
    font-size: 14px;
    position: absolute;
    top: 0px;
    left: 3px;
    color: white;
}
</style>