<template>
    <section class="tasks-sec">
        <div class="wrapper">
            <div class="row">
                <div class="title-col col">
                    <h1>Zadanie:</h1>
                </div>
                <div class="tasks-col col">
                    <ol>
                        <li class="done">Utworzyć klasę (kontener) do przechowywania listy obiektów i metodę służącą do losowego mieszania tablicy.</li>
                        <li class="done">Umieścić w kontenerze początkowo 6 obiektów które mają w sobie pole 'title' z różnymi tytułami.</li>
                        <li class="done">Napisać komponent w Vue wyświetlający zawartość kontenera w rzędach po 3 elementy wykorzystujący subkomponenty.</li>
                        <li class="done">Dodać w komponencie głównym przycisk wykonujący mieszanie elementów w kontenerze.</li>
                        <li class="done">Dodać w komponencie głównym pole typu 'input' służące do edycji pola 'title' w zaznaczonym aktualnie elemencie (zaznaczanie powinno odbywać się przez kliknięcie).</li>
                        <li class="done">Załączyć plik 'readme' z instrukcją uruchomienia systemu</li>
                    </ol>
                </div>
            </div>
        </div>
    </section>
</template>


<script>
export default {
    name: 'Tasks'
}
</script>

<style>
    .done {
        color: #1FD37C;
    }
</style>
