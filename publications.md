---
title: Publications 
layout: page 
permalink: /publications.html
class: publications
---

{% bibliography %}

<script>
function toggleDiv(divId, element) {
    var div = document.getElementById(divId);
    var svgIcons = element.querySelectorAll('svg.toggle-icon');
    
    if (div.style.display === "none") {
        div.style.display = "block";
        svgIcons[0].style.display = "none"; 
        svgIcons[1].style.display = "inline"; 
        // svgIcons[2].style.display = "inline"; 
    } else {
        div.style.display = "none";
        svgIcons[0].style.display = "inline"; 
        svgIcons[1].style.display = "none";
        // svgIcons[2].style.display = "none";
    }
}

function copyToClipboard(divId) {
    // Select the text
    var div = document.getElementById(divId + '-bibtex');
    const text = div.querySelector('pre').innerText;

    // Create a temporary textarea to hold the text
    const textarea = document.createElement('textarea');
    textarea.value = text;
    document.body.appendChild(textarea);
    textarea.select();
    document.execCommand('copy');
    document.body.removeChild(textarea);

    // Show the tooltip
    const tooltip = document.getElementById(divId + '-tooltip');
    tooltip.style.display = 'block';
    
    // Hide the tooltip after a short delay
    setTimeout(() => {
        tooltip.style.display = 'none';
    }, 2000); // Adjust the delay as needed
}
</script>
