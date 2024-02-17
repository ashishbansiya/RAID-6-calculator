<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RAID 6 Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }

        #calculator {
            max-width: 400px;
            margin: 0 auto;
        }

        label {
            display: block;
            margin-bottom: 8px;
        }

        input {
            width: 100%;
            padding: 8px;
            margin-bottom: 16px;
        }

        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px;
            border: none;
            cursor: pointer;
            width: 100%;
        }

        #result {
            margin-top: 20px;
        }
    </style>
</head>
<body>

<div id="calculator">
    <label for="numDrives">Number of Drives:</label>
    <input type="number" id="numDrives" placeholder="Enter number of drives" required>

    <label for="driveCapacity">Drive Capacity (GB):</label>
    <input type="number" id="driveCapacity" placeholder="Enter drive capacity" required>

    <label for="driveSpeed">Drive Speed (MB/s):</label>
    <input type="number" id="driveSpeed" placeholder="Enter drive speed" required>

    <button onclick="calculateRAID6()">Calculate RAID 6</button>

    <div id="result"></div>
</div>

<script>
    function calculateRAID6() {
        const numDrives = parseInt(document.getElementById("numDrives").value);
        const driveCapacity = parseInt(document.getElementById("driveCapacity").value);
        const driveSpeed = parseInt(document.getElementById("driveSpeed").value);

        const totalCapacity = (numDrives - 2) * driveCapacity; // RAID 6 uses two drives for parity
        const totalSpeed = (numDrives - 2) * driveSpeed; // RAID 6 uses two drives for parity

        const resultElement = document.getElementById("result");
        resultElement.innerHTML = `<p>RAID 6 Total Capacity: ${totalCapacity} GB</p>
                                   <p>RAID 6 Total Speed: ${totalSpeed} MB/s</p>`;
    }
</script>

</body>
</html>
