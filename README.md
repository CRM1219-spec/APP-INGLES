<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Repasa los Tiempos Verbales</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        .menu {
            margin-top: 50px;
        }
        .structure {
            display: none;
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <h1>Repasa los Tiempos Verbales en Inglés</h1>
    <div class="menu">
        <h2>Escoge el tiempo que quieres repasar</h2>
        <select id="verbTense" onchange="showStructure()">
            <option value="">Selecciona un tiempo verbal</option>
            <option value="presentSimple">Present Simple</option>
            <option value="presentContinuous">Present Continuous</option>
            <option value="presentPerfect">Present Perfect</option>
            <!-- Añadir más opciones según sea necesario -->
        </select>
    </div>

    <div id="structure" class="structure">
        <h3 id="tenseName"></h3>
        <p id="tenseStructure"></p>
        <h4>Ejemplos:</h4>
        <ul id="examples"></ul>
    </div>

    <script>
        const structures = {
            presentSimple: {
                name: "Present Simple",
                structure: "Subject + Base Verb (he/she/it + verb+s)",
                examples: [
                    "I work every day.",
                    "She plays tennis.",
                    "They study at school."
                ]
            },
            presentContinuous: {
                name: "Present Continuous",
                structure: "Subject + am/is/are + Verb-ing",
                examples: [
                    "I am working right now.",
                    "She is playing tennis.",
                    "They are studying at school."
                ]
            },
            presentPerfect: {
                name: "Present Perfect",
                structure: "Subject + have/has + past participle",
                examples: [
                    "I have worked here for five years.",
                    "She has played tennis.",
                    "They have studied the lesson."
                ]
            }
            // Puedes agregar más tiempos verbales aquí.
        };

        function showStructure() {
            const tense = document.getElementById('verbTense').value;
            if (tense) {
                const tenseData = structures[tense];
                document.getElementById('tenseName').textContent = tenseData.name;
                document.getElementById('tenseStructure').textContent = "Estructura: " + tenseData.structure;
                
                const examplesList = document.getElementById('examples');
                examplesList.innerHTML = "";
                tenseData.examples.forEach(example => {
                    const li = document.createElement('li');
                    li.textContent = example;
                    examplesList.appendChild(li);
                });

                document.getElementById('structure').style.display = 'block';
            } else {
                document.getElementById('structure').style.display = 'none';
            }
        }
    </script>

</body>
</html>
