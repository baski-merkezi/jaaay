let noClicks = 0;

document.getElementById('yesButton').addEventListener('click', function() {
    const message = document.getElementById('message');
    // Keep the "Yes" button message separate and update the message under the "Yes" button
    message.textContent = "YAY I LOVE YOU MY PRETTY GIRL YOURE THE BESTEST";
    // Keep the message near the "Yes" button
    const yesButton = document.getElementById('yesButton');
    message.style.position = 'absolute';
    message.style.left = `${yesButton.offsetLeft}px`;
    message.style.top = `${yesButton.offsetTop + yesButton.offsetHeight + 5}px`;
    message.style.fontSize = '16px';  // Make it bigger for "Yes" button message
});

document.getElementById('noButton').addEventListener('click', function() {
    noClicks++;
    const message = document.getElementById('message');
    message.textContent = "NO PLEASE JAY :(";

    // Make the button move to a random position
    const button = document.getElementById('noButton');
    const x = Math.random() * (window.innerWidth - 100);
    const y = Math.random() * (window.innerHeight - 100);
    button.style.position = 'absolute';
    button.style.left = `${x}px`;
    button.style.top = `${y}px`;

    // Position the message to follow the "No" button, under it
    message.style.position = 'absolute';
    message.style.left = `${x}px`;  // Align horizontally with the "No" button
    message.style.top = `${y + button.offsetHeight + 5}px`;  // Position below the button with a small gap
    message.style.fontSize = '16px';  // Slightly bigger text

    // After 3 clicks, disable the "No" button
    if (noClicks === 3) {
        message.textContent = "Aight lil bro enof.";
        button.disabled = true;
        button.style.opacity = '0.5';
        button.style.cursor = 'not-allowed';
    }
});
