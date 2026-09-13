# WEB-HACKATHON.HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Life RPG</title>

<style>
*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

body{
    font-family:Arial,sans-serif;
    background:#0b0815;
    color:white;
    min-height:100vh;
}

button,input,select{
    font:inherit;
}

button{
    cursor:pointer;
}

/* LOGIN */

.login{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:radial-gradient(circle at top,#3b1970,#0b0815 65%);
}

.login-box{
    width:90%;
    max-width:420px;
    padding:40px;
    text-align:center;
    background:#171126;
    border:1px solid #7045a8;
    border-radius:20px;
    box-shadow:0 0 40px #5b2ca055;
}

.login-box h1{
    font-size:35px;
    margin-bottom:10px;
}

.login-box p{
    color:#aaa;
    margin-bottom:25px;
}

input,select{
    width:100%;
    padding:14px;
    margin-bottom:15px;
    background:#0e0a19;
    color:white;
    border:1px solid #46316d;
    border-radius:10px;
}

button{
    border:none;
    border-radius:10px;
    padding:12px 18px;
    background:#8b5cf6;
    color:white;
    font-weight:bold;
}

button:hover{
    background:#a477ff;
    transform:translateY(-2px);
}

.hidden{
    display:none!important;
}

/* HEADER */

header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding:20px 7%;
    background:#120d20;
    border-bottom:1px solid #302044;
}

header h1{
    color:#b48cff;
}

header p{
    color:#999;
    margin-top:5px;
}

.logout{
    background:transparent;
    border:1px solid #654298;
}

/* MAIN */

main{
    width:86%;
    max-width:1200px;
    margin:30px auto;
}

/* CHARACTER */

.character{
    display:grid;
    grid-template-columns:90px 1fr auto auto;
    gap:20px;
    align-items:center;
    padding:25px;
    background:linear-gradient(135deg,#21143b,#151024);
    border:1px solid #49316e;
    border-radius:18px;
    margin-bottom:30px;
}

.avatar{
    width:75px;
    height:75px;
    display:flex;
    justify-content:center;
    align-items:center;
    border-radius:50%;
    background:#36215a;
    font-size:40px;
}

.level{
    color:#c5a8ff;
    margin:7px 0;
}

.xp{
    width:100%;
    height:12px;
    background:#08060d;
    border-radius:20px;
    overflow:hidden;
}

.xp div{
    width:0%;
    height:100%;
    background:linear-gradient(90deg,#7c3aed,#c084fc);
    transition:.5s;
}

.stats{
    background:#1a1229;
    padding:15px;
    border-radius:12px;
    color:#ffd76a;
}

/* SECTION */

.section{
    margin-top:30px;
}

.section-title{
    margin-bottom:18px;
}

.section-head{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:18px;
}

/* ATTRIBUTES */

.attributes{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:15px;
}

.attribute{
    text-align:center;
    background:#151020;
    border:1px solid #33244a;
    padding:20px;
    border-radius:14px;
    font-size:25px;
}

.attribute span{
    display:block;
    color:#999;
    font-size:14px;
    margin:8px;
}

.attribute strong{
    color:#c39cff;
}

/* QUEST */

.quest{
    display:flex;
    align-items:center;
    gap:15px;
    justify-content:space-between;
    background:#151020;
    border:1px solid #33244a;
    padding:18px;
    border-radius:14px;
    margin-bottom:12px;
    transition:.3s;
}

.quest:hover{
    transform:translateX(5px);
    border-color:#7651ae;
}

.quest-info{
    flex:1;
}

.quest-info p{
    color:#888;
    font-size:13px;
    margin-top:6px;
}

.reward{
    color:#d0a6ff;
    white-space:nowrap;
}

.complete{
    background:#22c55e;
}

.delete{
    background:#4a1d2a;
    color:#ff9caa;
    margin-left:5px;
}

/* TREASURE */

.treasures{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:15px;
}

.treasure{
    text-align:center;
    background:#151020;
    border:1px solid #33244a;
    padding:25px;
    border-radius:14px;
}

.treasure .icon{
    font-size:35px;
}

.treasure h3{
    margin:10px;
}

.treasure p{
    color:#777;
    font-size:13px;
}

/* MODAL */

.modal{
    position:fixed;
    inset:0;
    background:#000b;
    display:flex;
    justify-content:center;
    align-items:center;
    padding:20px;
}

.modal-box{
    width:100%;
    max-width:430px;
    padding:30px;
    background:#181126;
    border:1px solid #654298;
    border-radius:18px;
}

.modal-box h2{
    margin-bottom:20px;
}

.modal-buttons{
    display:flex;
    gap:10px;
}

.modal-buttons button{
    flex:1;
}

.cancel{
    background:#30253e;
}

/* LEVEL UP */

.levelup{
    position:fixed;
    top:30px;
    left:50%;
    transform:translateX(-50%);
    background:#8b5cf6;
    padding:20px 35px;
    border-radius:15px;
    font-size:22px;
    font-weight:bold;
    z-index:10;
    animation:pop .5s;
}

@keyframes pop{
    from{
        transform:translateX(-50%) scale(.5);
    }
    to{
        transform:translateX(-50%) scale(1);
    }
}

/* MOBILE */

@media(max-width:800px){

    .character{
        grid-template-columns:1fr;
        text-align:center;
    }

    .avatar{
        margin:auto;
    }

    .attributes{
        grid-template-columns:repeat(2,1fr);
    }

    .treasures{
        grid-template-columns:1fr;
    }

    .quest{
        flex-direction:column;
        align-items:flex-start;
    }
}

@media(max-width:500px){

    main{
        width:92%;
    }

    header{
        padding:18px 5%;
    }

    .attributes{
        grid-template-columns:1fr 1fr;
    }
}
</style>
</head>

<body>

<!-- LOGIN PAGE -->

<div id="loginPage" class="login">

    <div class="login-box">

        <h1>⚔️ LIFE RPG</h1>

        <p>
            Turn your everyday tasks into an adventure!
        </p>

        <input
            type="text"
            id="username"
            placeholder="Enter your name"
        >

        <button onclick="startGame()">
            START ADVENTURE
        </button>

    </div>

</div>


<!-- APPLICATION -->

<div id="app" class="hidden">

<header>

    <div>
        <h1>⚔️ LIFE RPG</h1>
        <p>
            Welcome, <span id="playerName"></span>!
        </p>
    </div>

    <button
        class="logout"
        onclick="logout()">
        Logout
    </button>

</header>


<main>

<!-- CHARACTER -->

<section class="character">

    <div class="avatar">
        🧙
    </div>

    <div>

        <h2 id="characterName">
            Adventurer
        </h2>

        <div class="level">
            Level <span id="level">1</span>
        </div>

        <div class="xp">
            <div id="xpBar"></div>
        </div>

        <small id="xpText">
            0 / 100 XP
        </small>

    </div>

    <div class="stats">
        🪙 <span id="gold">0</span> Gold
    </div>

    <div class="stats">
        🔥 <span id="streak">0</span> Days
    </div>

</section>


<!-- ATTRIBUTES -->

<section class="section">

<h2 class="section-title">
    ⚔️ Character Attributes
</h2>

<div class="attributes">

    <div class="attribute">
        💪
        <span>Strength</span>
        <strong id="strength">1</strong>
    </div>

    <div class="attribute">
        🧠
        <span>Intellect</span>
        <strong id="intellect">1</strong>
    </div>

    <div class="attribute">
        🎯
        <span>Discipline</span>
        <strong id="discipline">1</strong>
    </div>

    <div class="attribute">
        ❤️
        <span>Vitality</span>
        <strong id="vitality">1</strong>
    </div>

</div>

</section>


<!-- QUESTS -->

<section class="section">

<div class="section-head">

    <h2>
        📜 Active Quests
    </h2>

    <button onclick="openQuest()">
        + Add Quest
    </button>

</div>

<div id="questList"></div>

<p
    id="empty"
    style="text-align:center;color:#777;padding:25px;">
    No quests yet. Create your first quest!
</p>

</section>


<!-- TREASURE -->

<section class="section">

<h2 class="section-title">
    🏆 Treasure Room
</h2>

<div class="treasures">

    <div class="treasure">
        <div class="icon">🏅</div>
        <h3>First Quest</h3>
        <p>Complete your first quest</p>
    </div>

    <div class="treasure">
        <div class="icon">🔥</div>
        <h3>7 Day Warrior</h3>
        <p>Maintain a 7 day streak</p>
    </div>

    <div class="treasure">
        <div class="icon">⭐</div>
        <h3>Level 5</h3>
        <p>Reach Level 5</p>
    </div>

</div>

</section>

</main>

</div>


<!-- QUEST FORM -->

<div
    id="questModal"
    class="modal hidden">

    <div class="modal-box">

        <h2>📜 Create New Quest</h2>

        <input
            id="taskName"
            type="text"
            placeholder="Enter quest name">

        <select id="difficulty">

            <option value="easy">
                Easy — 25 XP
            </option>

            <option value="medium">
                Medium — 50 XP
            </option>

            <option value="hard">
                Hard — 100 XP
            </option>

            <option value="epic">
                Epic — 200 XP
            </option>

        </select>

        <select id="attribute">

            <option value="discipline">
                🎯 Discipline
            </option>

            <option value="strength">
                💪 Strength
            </option>

            <option value="intellect">
                🧠 Intellect
            </option>

            <option value="vitality">
                ❤️ Vitality
            </option>

        </select>

        <div class="modal-buttons">

            <button onclick="addQuest()">
                Create Quest
            </button>

            <button
                class="cancel"
                onclick="closeQuest()">
                Cancel
            </button>

        </div>

    </div>

</div>


<!-- LEVEL UP MESSAGE -->

<div
    id="levelUp"
    class="levelup hidden">

    🎉 LEVEL UP! 🎉

</div>


<script>

let game =
JSON.parse(localStorage.getItem("lifeRPG")) || {

    username:"",
    level:1,
    xp:0,
    gold:0,
    streak:0,

    attributes:{
        strength:1,
        intellect:1,
        discipline:1,
        vitality:1
    },

    quests:[],
    lastCompleted:null
};


// SAVE

function save(){

    localStorage.setItem(
        "lifeRPG",
        JSON.stringify(game)
    );

}


// START

function startGame(){

    let name =
    document.getElementById("username")
    .value.trim();

    if(name===""){

        alert("Please enter your name!");

        return;

    }

    game.username=name;

    save();

    document
    .getElementById("loginPage")
    .classList.add("hidden");

    document
    .getElementById("app")
    .classList.remove("hidden");

    update();

}


// LOGOUT

function logout(){

    document
    .getElementById("app")
    .classList.add("hidden");

    document
    .getElementById("loginPage")
    .classList.remove("hidden");

}


// XP REQUIRED

function requiredXP(){

    return 100 * game.level * game.level;

}


// UPDATE DASHBOARD

function update(){

    document.getElementById("playerName")
    .textContent=game.username;

    document.getElementById("characterName")
    .textContent=game.username;

    document.getElementById("level")
    .textContent=game.level;

    document.getElementById("gold")
    .textContent=game.gold;

    document.getElementById("streak")
    .textContent=game.streak;

    document.getElementById("strength")
    .textContent=game.attributes.strength;

    document.getElementById("intellect")
    .textContent=game.attributes.intellect;

    document.getElementById("discipline")
    .textContent=game.attributes.discipline;

    document.getElementById("vitality")
    .textContent=game.attributes.vitality;


    let needed=requiredXP();

    let percent=
    (game.xp/needed)*100;

    document.getElementById("xpBar")
    .style.width=
    Math.min(percent,100)+"%";

    document.getElementById("xpText")
    .textContent=
    game.xp+" / "+needed+" XP";


    showQuests();

}


// OPEN QUEST

function openQuest(){

    document
    .getElementById("questModal")
    .classList.remove("hidden");

}


// CLOSE QUEST

function closeQuest(){

    document
    .getElementById("questModal")
    .classList.add("hidden");

}


// ADD QUEST

function addQuest(){

    let name=
    document
    .getElementById("taskName")
    .value.trim();

    let difficulty=
    document
    .getElementById("difficulty")
    .value;

    let attribute=
    document
    .getElementById("attribute")
    .value;


    if(name===""){

        alert("Enter quest name!");

        return;

    }


    let xp=25;

    if(difficulty==="medium")
        xp=50;

    if(difficulty==="hard")
        xp=100;

    if(difficulty==="epic")
        xp=200;


    game.quests.push({

        id:Date.now(),

        name:name,

        difficulty:difficulty,

        attribute:attribute,

        xp:xp,

        completed:false

    });


    save();

    document
    .getElementById("taskName")
    .value="";

    closeQuest();

    update();

}


// SHOW QUESTS

function showQuests(){

    let list=
    document.getElementById("questList");

    let empty=
    document.getElementById("empty");


    list.innerHTML="";


    if(game.quests.length===0){

        empty.classList.remove("hidden");

        return;

    }


    empty.classList.add("hidden");


    game.quests.forEach(function(q){

        let div=
        document.createElement("div");

        div.className="quest";


        let icon="🎯";

        if(q.attribute==="strength")
            icon="💪";

        if(q.attribute==="intellect")
            icon="🧠";

        if(q.attribute==="vitality")
            icon="❤️";


        div.innerHTML=`

            <div class="quest-info">

                <h3>
                    ${icon} ${q.name}
                </h3>

                <p>
                    ${q.difficulty.toUpperCase()}
                    • ${q.attribute}
                </p>

            </div>

            <div class="reward">
                ⭐ ${q.xp} XP
            </div>

            <button
                class="complete"
                onclick="completeQuest(${q.id})">

                ${q.completed
                ? "Completed ✓"
                : "Complete"}

            </button>

            <button
                class="delete"
                onclick="deleteQuest(${q.id})">

                🗑

            </button>

        `;


        if(q.completed){

            div.style.opacity="0.5";

        }


        list.appendChild(div);

    });

}


// COMPLETE QUEST

function completeQuest(id){

    let quest=
    game.quests.find(
        q=>q.id===id
    );


    if(!quest || quest.completed)
        return;


    quest.completed=true;


    // XP

    game.xp+=quest.xp;


    // GOLD

    game.gold+=
    Math.floor(quest.xp*0.4);


    // ATTRIBUTE

    game.attributes[
        quest.attribute
    ]++;


    // STREAK

    updateStreak();


    // LEVEL

    checkLevel();


    save();

    update();

}


// LEVEL SYSTEM

function checkLevel(){

    let levelUp=false;


    while(
        game.xp>=requiredXP()
    ){

        game.xp-=requiredXP();

        game.level++;

        levelUp=true;

    }


    if(levelUp){

        let box=
        document.getElementById("levelUp");

        box.classList.remove("hidden");


        setTimeout(function(){

            box.classList.add("hidden");

        },2500);

    }

}


// STREAK

function updateStreak(){

    let today=
    new Date().toDateString();


    if(game.lastCompleted===today)
        return;


    if(game.lastCompleted===null){

        game.streak=1;

    }

    else{

        let old=
        new Date(game.lastCompleted);

        let current=
        new Date(today);

        let days=
        Math.floor(
            (current-old)/
            (1000*60*60*24)
        );


        if(days===1){

            game.streak++;

        }

        else if(days>1){

            game.streak=1;

        }

    }


    game.lastCompleted=today;

}


// DELETE

function deleteQuest(id){

    game.quests=
    game.quests.filter(
        q=>q.id!==id
    );

    save();

    update();

}


// LOAD SAVED GAME

window.onload=function(){

    if(game.username!==""){

        document
        .getElementById("loginPage")
        .classList.add("hidden");

        document
        .getElementById("app")
        .classList.remove("hidden");

        update();

    }

};

</script>

</body>
</html>
```
