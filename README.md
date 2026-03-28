function checkLeapYear() {
    let yr = document.getElementById("yearInput").value;
    
    if(!yr || isNaN(yr) || yr < 0) {
        showResult("Enter valid year! ❌", "not-leap");
        return;
    }
    
    yr = Number(yr);
    
    // Complete leap year logic
    if((yr % 4 === 0 && yr % 100 !== 0) || (yr % 400 === 0)) {
        showResult(`🎉 ${yr} is a LEAP YEAR! ✅`, "leap");
    } else {
        showResult(`❌ ${yr} is NOT a leap year`, "not-leap");
    }
}

function showResult(message, type) {
    document.getElementById("result").innerHTML = message;
    document.getElementById("result").className = `result ${type}`;
}

function clearInput() {
    document.getElementById("yearInput").value = "";
    document.getElementById("result").innerHTML = "";
}

// Enter key support
document.getElementById("yearInput").addEventListener("keypress", function(e) {
    if(e.key === "Enter") {
        checkLeapYear();
    }
});
