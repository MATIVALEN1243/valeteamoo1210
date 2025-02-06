<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Razones para Amarte</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 50px;
            background-color: #ffe6e6;
        }
        h1 {
            color: #ff4d4d;
        }
        button {
            background-color: #ff4d4d;
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 18px;
            cursor: pointer;
            border-radius: 10px;
            margin-top: 20px;
        }
        button:hover {
            background-color: #ff3333;
        }
        ul {
            list-style: none;
            padding: 0;
        }
        li {
            background: white;
            padding: 10px;
            margin: 5px auto;
            width: 50%;
            border-radius: 5px;
            box-shadow: 2px 2px 5px rgba(0,0,0,0.1);
        }
    </style>
</head>
<body>
    <h1>Razones para amarte</h1>
    <button id="boton" onclick="agregarRazon()">Te amo por...</button>
    <button id="boton-anterior" onclick="mostrarAnterior()">Anterior</button>
    <ul id="lista-razones"></ul>

    <script>
        const razones = [
            "Tu sonrisa", "Tu pelo", "Tu risa", "Tu humor", "Tu mirada", "Tu forma de ser", "Tus ojos", "Tus labios", "La confianza que me das", "Eres bonita",
            "Eres preciosa", "Eres linda", "Eres divertida", "Eres inteligente", "Tu lealtad", "Eres hermosa", "Tu pasión", "Tu fortaleza", "Tu honestidad", "Tu energía",
            "El apoyo que me das", "Tu creatividad", "Eres única", "Tu habilidad para hacerme reír", "Tu hermoso corazón", "Tu calidez", "Tu estilo", "Tu encanto",
            "Tu energía positiva", "La paciencia que tienes conmigo", "Tu sensibilidad", "Tus abrazos de paz y tranquilidad", "Tu preocupación por mí", "Tu apreciación",
            "Tu curiosidad", "Tu amor por mí", "Tu amor", "Mi motivación a seguir", "Tu presencia", "Tu alma", "Tu confianza en mí", "Tu lado amoroso", "Tu niña interior",
            "Tu cariño por tus amigas", "Te amo cada segundo más", "Eres atenta", "Eres cariñosa", "Nuestras locuras juntas", "Hacerme feliz", "Tus buenos días y buenas noches",
            "Tu pasión por lo que amas", "Tu atención", "Tu respeto", "Tus bromas", "Tu encanto", "Tu gracia", "Tu tranquilidad", "No me juzgas", "Eres mi mejor amiga",
            "Te puedo contar todo", "Nuestra conexión única", "Nuestro vínculo", "Tu crecimiento", "Tu esfuerzo por todo", "Tú", "Tu responsabilidad", "Tu interés",
            "Tus 'defectos' que para mí no lo son", "Tu piel", "Tus besitos", "Tus curiosidad", "Tus consejos", "Tus modales", "Tu cariño hacia mí", "Tu amor", "Tu perfección",
            "Tu aroma", "Tu perdón", "Me hiciste mejor persona", "Eres encantadora", "Tu amor", "Tu valor", "Haces todo por mí", "Tu existencia", "Tu cuerpo", "Tu personalidad",
            "Tu dulzura", "Sacas lo mejor de mí", "Volviste a mi niña interior", "Me haces sentir segura", "Tu astucia", "Te das cuenta cuando me pasa algo", "Eres generosa",
            "Eres talentosa", "Eres extrovertida", "La forma en que me miras", "Las cosas que aprendí de ti", "Tu compromiso", "Eres especial", "Eres un ángel", "Eres un regalo de la vida",
            "Eres educada", "Eres adorable", "Tú siendo tú", "Tú cuando me miras 🥹", "Tú con pelo largo", "Tú con pelo corto", "Tus bromas que me hacen reír", "Nuestras salidas",
            "Nuestras anécdotas", "Nuestras charlas", "Tú durmiendo", "Tus cariñitos", "Nuestros abrazos", "Haces todo por mí", "Sabes todo de mí", "Eres maravillosa",
            "Estás cuando te necesito", "Siempre quieres verme", "Tus logros", "Tu compañía", "Tu preocupación por mí", "Tu consuelo", "Me amas a pesar de todo lo que pasó con nosotras",
            "Me amas en todo momento", "Eres lo mejor que me pasó", "Tu belleza", "Tu calma", "Tu corazón", "Eres increíble", "Me enamoraste al instante", "Me haces reír",
            "Te amo solo a ti", "Te miro con ojos de amor solo a ti", "Me encanta tenerte en mi vida", "Me acompañas en todo", "Eres mi 'ojalá estuvieras aquí'", "Amo estar contigo",
            "Eres, y serás siempre, el amor de mi vida", "Me cumples todos los caprichos", "Dos días sin verte para mí son dos meses", "El día que nos conocimos", "Alegras mis días",
            "Amo cómo me miras", "Puedo ser yo misma contigo", "No te tengo vergüenza", "Somos un equipo", "Me llenas de amor", "Conocerte fue lo más lindo", "Tu amor",
            "Eres la luz en mi oscuridad", "Tú para mí, yo para ti", "Me enamoras cada día más", "Todas las canciones de amor me recuerdan a ti", "Me gustas mucho", "Amo tu voz",
            "Te elegí, y te voy a elegir siempre", "Me ayudas en todo", "Aunque me hagas enojar, sin ti no puedo estar", "Haces todo siempre más divertido y fácil", "Tu carisma",
            "Tu amabilidad", "Tu empatía", "Tu amor por los animales", "Tu cariño", "Tu corazón", "Tu amor", "Amo nuestra relación", "Tienes todo lo que quise", "Eres mi mejor coincidencia"
        ];
        let indice = 0;

        function agregarRazon() {
            const boton = document.getElementById("boton");
            const lista = document.getElementById("lista-razones");
            
            if (indice < razones.length) {
                const nuevaRazon = document.createElement("li");
                nuevaRazon.textContent = razones[indice];
                lista.appendChild(nuevaRazon);
                indice++;
                boton.textContent = "Te amo por... (" + indice + " de " + razones.length + ")";
            } else {
                boton.textContent = "Ya no hay más razones, te amo ❤️";
            }
        }

        function mostrarAnterior() {
            const boton = document.getElementById("boton");
            const lista = document.getElementById("lista-razones");

            if (indice > 0) {
                indice--;
                const items = lista.getElementsByTagName('li');
                lista.removeChild(items[items.length - 1]);
                boton.textContent = "Te amo por... (" + indice + " de " + razones.length + ")";
            }
        }
    </script>
</body>
</html>
