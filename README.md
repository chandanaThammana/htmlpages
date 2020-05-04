
<html>

<script type="text/javascript">
    var i=0;

    function AddressRegister(Name,Type,Address,Email,Mobile,Location)
    {
        this.Name = Name;
        this.Type = Type;
        this.Address = Address;
        this.Email = Email;
        this.Mobile = Mobile;
        this.Location = Location;
    }
    var flag = 0;
    var tabledata,button;
    var dataArray = new Array();
    function Add()
    {
        var Name=document.getElementById("name").value;
        var Types=document.getElementsByName("type");
        for(i = 0; i < Types.length; i++) {
            if(Types[i].checked)
                var Type = Types[i].value;
        }
        var Address=document.getElementById("address").value;
        var Email=document.getElementById("email").value;
        var Mobile=document.getElementById("mobile").value;
        var Location=document.getElementById("location").value;
        
        var data = new AddressRegister(Name,Type,Address,Email,Mobile,Location);
        dataArray.push(data);
        displayAddress();
    }
    function displayAddress()
    {
        if(flag==0)
        {
            tabledata = "<table style='position: fixed; background-color:lightgrey; border: 1px solid black; border-collapse: collapse;  margin-top: 25px;' border = '1'><tr><th>Name</th><th>Type</th><th>Address</th><th>Email</th><th>Mobile</th><th>Location</th></tr>";
        }

        for(i=0;i<dataArray.length;i++)
        {
         var tempname=dataArray[i].Name;
         var temptype=dataArray[i].Type;
         var tempaddress=dataArray[i].Address;
         var tempemail=dataArray[i].Email;
         var tempmobile=dataArray[i].Mobile;
         var templocation=dataArray[i].Location;
         
//Please fill the required code to store the values in tabledata.
tabledata=tabledata+"<tr><td>"+tempname+"</td><td>"+temptype+"</td><td>"+tempaddress+"</td><td>"
+tempemail+"</td><td>"+tempmobile+"</td><td>"+templocation+"</td></tr>";
}

    //console.log(tabledata);
    if(flag==0){  
    //Please fill the required code to store the table data in result.
    document.getElementById("result").innerHTML=tabledata;

    document.getElementById("name").value = "";
    
    document.getElementsByName("type").checked = false;

    document.getElementById("address").value = "";

    document.getElementById("email").value ="";
    
    document.getElementById("mobile").value ="";

    document.getElementById("location").value = "";
}
count=0;

}
</script>
<style>
body{
    background-color: #F8F8FA;
}
h1{
    text-align: center;
    color:#006666;
    font-family: Verdana;
}
</style>

<body>
    <h1>ADDRESS BOOK</h1>
    <table>
        <tr><td><label>Name</label></td>
            <td><input type="text" id="name" name="name" placeholder="Enter the name" pattern="[a-zA-Z ]{1,}" required></td></tr>
            <tr><td><label>Type</label></td>
                <td><input type="radio" id="type1" name="type" value="Temporary" required>Temporary
                    <input type="radio" id="type2" name="type" value="Permanent" required>Permanent
                </td></tr>
                <tr><td><label>Address</label></td>
                    <td><textarea name="address" id="address" placeholder="Fill Address here" required></textarea></td></tr>
                    <tr><td><label>Email</label></td>
                        <td><input type="text" id="email" name="email" placeholder="abc@gmail.com" pattern="[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}" required></td></tr>
                        <tr><td><label>Telephone/ Mobile Number</label></td>
                            <td><input type="text" name="mobile" id="mobile" placeholder="Enter the Mobile Number" pattern="[789][0-9]{9}" required></td></tr>
                            <tr><td><label>Location</label></td>
                                <td><select id="location" name="location" required>
                                    <option value="Coimbatore">Coimbatore</option>
                                    <option value="Chennai">Chennai</option>
                                    <option value="Bangalore">Bangalore</option>
                                </select></td></tr>
                                <tr><td><input type="submit" name="submit" id="submit" value="Add" onclick="Add();"></td>
                                    <td><input type="reset" name="clear" id="clear" value="Reset"></td></tr>
                                </table>
                                <div id="result"></div>
                            </body>
                            </html>
