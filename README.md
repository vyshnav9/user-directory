# user-directory
<html>
<head>
<title>User Directory</title>
</head>

<body style="font-family:Arial; text-align:center; background:#f4f6f8;">

<h2>Apartment User Directory</h2>

<div style="border:1px solid #ccc;margin:15px;padding:15px;border-radius:12px;background:white; width:300px; margin:auto;">

<h3>Enter Your Details</h3>

<input type="text" id="name" placeholder="Enter Name" style="margin:5px;"><br>
<input type="text" id="flat" placeholder="Enter Flat No" style="margin:5px;"><br><br>

<button onclick="goLocation()">View Location</button>

</div>

<script>
// Predefined users database
const users = [
    {name:"Aarav Sharma", flat:"A-101", location:"12.9716,77.5946"},
    {name:"Diya Patel", flat:"B-202", location:"19.0760,72.8777"},
    {name:"Rohan Das", flat:"C-303", location:"28.7041,77.1025"},
    {name:"Sneha Iyer", flat:"D-404", location:"13.0827,80.2707"},
    {name:"Karan Mehta", flat:"E-505", location:"22.5726,88.3639"}
];

function goLocation() {
    let name = document.getElementById("name").value.trim();
    let flat = document.getElementById("flat").value.trim();

    if(name=="" || flat==""){
        alert("Please enter name and flat number");
        return;
    }

    // find matching user
    let user = users.find(u => 
        u.name.toLowerCase() === name.toLowerCase() &&
        u.flat.toLowerCase() === flat.toLowerCase()
    );

    if(user){
        window.open("https://maps.google.com/?q=" + user.location);
    }
    else{
        alert("User not found!");
    }
}
</script>

</body>
</html>
