# Cómo usar el grid de Bootstrap

En este ejemplo se muestran los resultado de una liguilla de ajedrez utilizando para ello el grid de Bootstrap.
Para poder utilizarlo, previamente habremos incrustrado del framework de Bootstrap en el proyecto mediante el comando

        mpm install

ejecutandolo desde una ventana de comandos situados en la carpeta del proyecto.

El grid es responsive lo que nos permite cambiar el tamaño y que se mantenga la estructura

![Imagen maximizada](https://github.com/ialcaidef/GridExample/blob/master/grid%20images/expand.png)

~~~
<head>
    <meta name="viewport" content="width=device-width" />
    <title>Index</title>
    <link href="~/node_modules/bootstrap/dist/css/bootstrap.css" rel="stylesheet" />
    <link href="~/css/style.css" rel="stylesheet" />
</head>
<body>
    <div class="title">
        <h1>Chess League</h1>
        <p>Hey, These are the Results</p>
    </div>
    <div class="container">
        <div class="row grid-header align-items-center">
            <div class="col-2">
            </div>
            <div class="col-4">
                Competitors
            </div>
            <div class="col-3">
                Quantity
            </div>
            <div class="col-3">
                Results
            </div>
        </div>
        <div class="row align-items-center">
            @foreach (var item in Model)
            {
                <div class="col-2">
                    <div class="row justify-content-center">
                        <img src="~/images/@item.FirstCompetitorPhotoFileName" />
                    </div>
                    <div class="row justify-content-center">
                        <img src="~/images/@item.SecondCompetitorPhotoFileName" />
                    </div>
                </div>
                <div class="col-4">
                    <div class="row">
                        @Html.DisplayFor(model => item.FirstCompetitorName)
                    </div>
                    <div class="row">
                        @Html.DisplayFor(model => item.SecondCompetitorName)
                    </div>
                </div>
                <div class="col-3">
                    @Html.DisplayFor(model => item.GamesQuantity)
                </div>
                <div class="col-3">
                    @Html.DisplayFor(model => item.FinalScore)
                </div>
            }
        </div>
    </div>
    <script src="~/node_modules/jquery/dist/jquery.js"></script>
    <script src="~/node_modules/popper.js/dist/umd/popper.js"></script>
    <script src="~/node_modules/bootstrap/dist/js/bootstrap.js"></script>
</body>
~~~
