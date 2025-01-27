# intract-bot-quests

# open https://www.intract.io/?referralCode=2STqjs&referralSource=REFERRAL_PAGE&referralLink=https%3A%2F%2Fwww.intract.io%2Freferral
# open inspeksi = console = type "allow pasting" and enter = copy scrip paste in console

```bash
function clickTasksAndVerify() {
    const taskElements = document.querySelectorAll('._accordian_base_container_1vd77_1');

    if (taskElements.length === 0) {
        console.log('No task elements found.');
        return;
    }

    taskElements.forEach((taskElement, index) => {
        taskElement.addEventListener('click', (event) => {
            event.preventDefault();
            event.stopPropagation();
        }, true);
        taskElement.click();
        console.log(`Clicked on task element ${index + 1}`);
    });

    console.log(`Clicked on ${taskElements.length} task element(s) in total.`);

    setTimeout(() => {
        const verifyButtons = document.querySelectorAll('button[data-verify-button-status="idle"]._container_1b13v_1');

        if (verifyButtons.length === 0) {
            console.log('No verify buttons found.');
            return;
        }

        verifyButtons.forEach((verifyButton, index) => {
            verifyButton.click();
            console.log(`Clicked on verify ${index + 1}`);
        });

        console.log(`Clicked on ${verifyButtons.length} verify (s) in total.`);
    }, 8000);
}

clickTasksAndVerify();

```
