# GST-Calculator
Its a GST calculator used in grossery stores 

-----------------------------------------------------HTML Code ----------------------------------------------------------------
<!DOCTYPE html>
<html>
    <head>
        <title>GST CALCULATOR</title>
		<h2 style="color:brown;"><b>GROCERY STORE GST CALCULATOR</b></h2>
		<style>
		input{
				background-color:lightgreen;
				color:black;
			}
		body{
				background-color: lightblue;
			}
</style>
		
    </head>
    <body>
        <div class="inp">
            <label for="price">Price (before GST): </label>
            <input id="price" type="number" value="  " />
        </div>
        <div class="inp">
            <label for="gst">GST rate (%): </label>
            <input id="gst" type="number" value="  "  />
        </div>
        <div class="inp">
            <button onclick="inpChange()">Calculate</button>
        </div>
        
        <div class="inp">
            <label for="priceGst">Price (GST inclusive) : </label>
            <input id="priceGst" type="number" readonly />
        </div>
        
        <script>
            priceEle = document.getElementById("price");
            gstEle = document.getElementById("gst");
            priceGstEle = document.getElementById("priceGst");
            
            function calculateGst(price, tax) {
                return (price * tax/100) + price;
            }    
            
            function inpChange() {
                if(!isNaN(priceEle.value) && !isNaN(gstEle.value)) {
                    price = Number(priceEle.value);
                    gst = Number(gstEle.value);
                    priceGstEle.value = calculateGst(price, gst).toFixed(2);
                }
            }
            
            inpChange();
            
        </script>
        
    </body>
</html>
