HTML CODE
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Age Calculator</title>
</head>
<body>
    <h1>Age Calculator</h1>
    <form id="ageForm">
        <label for="day">Day:</label>
        <input type="number" id="day" name="day" min="1" max="31" required>
        <br>
        <label for="month">Month:</label>
        <input type="number" id="month" name="month" min="1" max="12" required>
        <br>
        <label for="year">Year:</label>
        <input type="number" id="year" name="year" required>
        <br>
        <button type="button" onclick="calculateAge()">Calculate Age</button>
    </form>
    <p id="result"></p>

    <script src="ageCalculator.js"></script>
</body>
</html>





JAVASCRIPT CODE
function calculateAge() {
    const day = parseInt(document.getElementById('day').value);
    const month = parseInt(document.getElementById('month').value);
    const year = parseInt(document.getElementById('year').value);

    const today = new Date();
    const birthDate = new Date(year, month - 1, day);

    let age = today.getFullYear() - birthDate.getFullYear();
    const monthDifference = today.getMonth() - birthDate.getMonth();

    if (monthDifference < 0 || (monthDifference === 0 && today.getDate() < birthDate.getDate())) {
        age--;
    }

    document.getElementById('result').innerText = `Your age is ${age} years old.`;
}
