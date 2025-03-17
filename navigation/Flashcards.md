---
layout: page
permalink: /flashcards/
---

<html lang="en">
<head>
    <title>Flashcards</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background-color: #f4f4f4;
        }
        .container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            padding: 20px;
        }
        .card {
            width: 250px;
            height: 150px;
            perspective: 1000px;
            cursor: pointer;
        }
        .card-inner {
            width: 100%;
            height: 100%;
            text-align: center;
            transition: transform 0.6s;
            transform-style: preserve-3d;
            position: relative;
        }
        .card.flipped .card-inner {
            transform: rotateY(180deg);
        }
        .card-front, .card-back {
            width: 100%;
            height: 100%;
            position: absolute;
            backface-visibility: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            font-size: 18px;
            padding: 10px;
            text-align: center;
        }
        .card-front {
            background-color: #007bff;
            color: white;
        }
        .card-back {
            background-color: white;
            color: #333;
            border: 2px solid #007bff;
            transform: rotateY(180deg);
        }
    </style>
</head>
<body>

    <h1>Flashcards</h1>
    <div class="container" id="flashcard-container"></div>

    <script>
        const terms = [
            { term: "AI Art", definition: "AI Art is a form of artistic expression created with artificial intelligence technology." },
            { term: "Creative Commons", definition: "Creative Commons is a licensing system allowing creators to share their work with specific permissions." },
            { term: "Digital Divide", definition: "The gap between those who have access to digital technology and those who do not." },
            { term: "Echo Chambers", definition: "Online environments where individuals are exposed only to ideas that reinforce their existing beliefs." },
            { term: "Fair Use", definition: "A legal doctrine that allows limited use of copyrighted material without permission." },
            { term: "First Amendment", definition: "Part of the U.S. Constitution that guarantees freedoms like speech, religion, and press." },
            { term: "Intellectual Property", definition: "Creations of the mind, such as inventions, designs, and artistic works, protected by law." },
            { term: "Misinformation", definition: "False or inaccurate information that is spread unintentionally or deliberately." },
            { term: "Moral Rights", definition: "Legal rights that creators have over their work, including authorship and integrity." },
            { term: "Open Sourcing", definition: "Making source code available to the public to encourage collaboration and transparency." },
            { term: "Open Access", definition: "Unrestricted online access to scholarly research articles." },
            { term: "Plagiarism", definition: "Using someone else's words or ideas without proper credit." }
        ];

        const container = document.getElementById("flashcard-container");

        terms.forEach(({ term, definition }) => {
            const card = document.createElement("div");
            card.classList.add("card");
            card.innerHTML = `
                <div class="card-inner">
                    <div class="card-front">${term}</div>
                    <div class="card-back">${definition}</div>
                </div>
            `;
            card.addEventListener("click", () => card.classList.toggle("flipped"));
            container.appendChild(card);
        });
    </script>

</body>
</html>
