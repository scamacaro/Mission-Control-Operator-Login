# Mission-Control-Operator-Login
Mission Control Operator Login
<!--This is a webpage made to fulfil assignment for CS102, 
    Mission Control Operator Login
Sanyerlis Camacaro     sancamac@uat.edu-->
<!DOCTYPE html>
<html>
<!--Login-->

<head>
    <!--Style for page-->
    <script src=loginCode.js></script>
    <link href="Loginstyle.css" rel="stylesheet" type="text/css" />
    <title>
        UAT Space Login
    </title>
</head>

<body>
    <!--Welcome line-->
    <h1>
        Welcome to UAT Space Login
    </h1>

    <!--Display login status-->
    <p id="loginStatus">
        Status of Login...
    </p>
    <br>
    <!--Form for First/Last Name and Badge ID Submission buttons-->
    <form id="creditSubmit" onsubmit="return false">
        First name: <input type="text" id="fName" /><br>
        Last name: <input type="text" id="lName" /><br>
        Badge Number: <input type="number" id="badgeID" /><br>
        <input type="submit" onclick="checkCreds();" />

    </form>

</body>


</html>


body {
    background-color: white;
    background-image: linear-gradient(90deg, white 0%, rgb(57, 107, 160));
}



function checkCreds() {
    //Box to store First Names
    var firstName = document.getElementById("fName").value;
    //Box to store Last Names
    var lastName = document.getElementById("lName").value;
    //Box to store badge ID
    var badgeNumb = document.getElementById("badgeID").value;
    //Displays Full Name when is granted to page
    var fullName = firstName + " " + lastName;

    //If input names or badge ID are incorrect display error
    if (fullName.length > 20 || fullName.length == 1) {
        document.getElementById("loginStatus").innerHTML = "Full Name has too many characters, Try again.";
    }
    else if (badgeNumb > 999 || badgeNumb < 1) {
        document.getElementById("loginStatus").innerHTML = "Invalid Badge Number.";
    }
    else {
        //if they're correct direct to programming data buttons
        alert("Access granted! Welcome " + fullName);
        location.replace("programming buttons.html");
    }

} 
