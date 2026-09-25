<script>
    import Navbar from '$lib/components/navbar.svelte';
    import Footer from '$lib/components/footer.svelte';
    import Header from '$lib/components/header.svelte';

    let Estudiantes = $state({
        nombre: '',
        apellido: '',
        edad: ''
    });

    let listaEstudiantes = $state([]);

    let mostrarDatos = $state(false);


    function handleClick() {

        // Verificamos que los campos estén llenos
        if (
            Estudiantes.nombre === '' ||
            Estudiantes.apellido === '' ||
            Estudiantes.edad === ''
        ) {
            alert('Por favor, completa todos los campos.');
            return;
        }

        // Guardamos una copia del estudiante
        listaEstudiantes.push({
            nombre: Estudiantes.nombre,
            apellido: Estudiantes.apellido,
            edad: Estudiantes.edad
        });

        mostrarDatos = true;

        // Limpiamos el formulario
        Estudiantes.nombre = '';
        Estudiantes.apellido = '';
        Estudiantes.edad = '';
    }


    function eliminarEstudiante(indice) {

        listaEstudiantes.splice(indice, 1);

    }
</script>


<Navbar />


<div class="container py-5">

    <!-- ENCABEZADO -->
    <div class="mb-4">

        <h1 class="fw-bold titulo">
            Estudiantes
        </h1>

        <p class="text-secondary">
            Registra y consulta los estudiantes pertenecientes a los semilleros.
        </p>

    </div>


    <div class="row g-4">

        <!-- FORMULARIO -->
        <div class="col-12 col-lg-5">

            <div class="card formulario-card">

                <div class="card-body p-4">

                    <div class="icono-formulario mb-3">
                        <i class="bi bi-person-plus-fill"></i>
                    </div>

                    <h3 class="fw-bold">
                        Registrar estudiante
                    </h3>

                    <p class="text-secondary mb-4">
                        Completa la información del estudiante.
                    </p>


                    <form onsubmit={(e) => {
                        e.preventDefault();
                        handleClick();
                    }}>

                        <!-- NOMBRE -->
                        <div class="mb-3">

                            <label
                                for="nombre"
                                class="form-label fw-semibold"
                            >
                                Nombre
                            </label>

                            <input
                                type="text"
                                id="nombre"
                                bind:value={Estudiantes.nombre}
                                class="form-control"
                                placeholder="Escribe el nombre"
                            />

                        </div>


                        <!-- APELLIDO -->
                        <div class="mb-3">

                            <label
                                for="apellido"
                                class="form-label fw-semibold"
                            >
                                Apellido
                            </label>

                            <input
                                type="text"
                                id="apellido"
                                bind:value={Estudiantes.apellido}
                                class="form-control"
                                placeholder="Escribe el apellido"
                            />

                        </div>


                        <!-- EDAD -->
                        <div class="mb-4">

                            <label
                                for="edad"
                                class="form-label fw-semibold"
                            >
                                Edad
                            </label>

                            <input
                                type="number"
                                id="edad"
                                bind:value={Estudiantes.edad}
                                class="form-control"
                                placeholder="Escribe la edad"
                                min="1"
                            />

                        </div>


                        <!-- BOTÓN -->
                        <button
                            type="submit"
                            class="btn btn-primary w-100"
                        >

                            <i class="bi bi-save me-2"></i>

                            Guardar estudiante

                        </button>

                    </form>

                </div>

            </div>

        </div>


        <!-- LISTA -->
        <div class="col-12 col-lg-7">

            <div class="card estudiantes-card h-100">

                <div class="card-body p-4">

                    <div class="d-flex justify-content-between align-items-center mb-4">

                        <div>

                            <h3 class="fw-bold mb-1">
                                Estudiantes registrados
                            </h3>

                            <p class="text-secondary mb-0">
                                Lista de estudiantes agregados.
                            </p>

                        </div>

                        <span class="cantidad">
                            {listaEstudiantes.length}
                        </span>

                    </div>


                    {#if listaEstudiantes.length === 0}

                        <!-- CUANDO NO HAY ESTUDIANTES -->

                        <div class="vacio">

                            <div class="icono-vacio">

                                <i class="bi bi-people"></i>

                            </div>

                            <h5 class="fw-bold mt-3">
                                No hay estudiantes registrados
                            </h5>

                            <p class="text-secondary mb-0">
                                Agrega un estudiante usando el formulario.
                            </p>

                        </div>


                    {:else}

                        <!-- TABLA -->

                        <div class="table-responsive">

                            <table class="table align-middle">

                                <thead>

                                    <tr>

                                        <th>Estudiante</th>

                                        <th>Edad</th>

                                        <th class="text-end">
                                            Acción
                                        </th>

                                    </tr>

                                </thead>


                                <tbody>

                                    {#each listaEstudiantes as estudiante, i}

                                        <tr>

                                            <td>

                                                <div class="d-flex align-items-center gap-3">

                                                    <div class="avatar">

                                                        <i class="bi bi-person-fill"></i>

                                                    </div>


                                                    <div>

                                                        <div class="fw-semibold">
                                                            {estudiante.nombre}
                                                            {estudiante.apellido}
                                                        </div>

                                                        <small class="text-secondary">
                                                            Estudiante
                                                        </small>

                                                    </div>

                                                </div>

                                            </td>


                                            <td>

                                                <span class="edad">
                                                    {estudiante.edad} años
                                                </span>

                                            </td>


                                            <td class="text-end">

                                                <button
                                                    class="btn btn-sm btn-outline-danger"
                                                    onclick={() => eliminarEstudiante(i)}
                                                >

                                                    <i class="bi bi-trash" aria-hidden="true"></i>

                                                </button>

                                            </td>

                                        </tr>

                                    {/each}

                                </tbody>

                            </table>

                        </div>

                    {/if}

                </div>

            </div>

        </div>

    </div>


    <!-- AVISO -->
    {#if mostrarDatos && listaEstudiantes.length > 0}

        <div class="alert alert-success mt-4 d-flex align-items-center">

            <i class="bi bi-check-circle-fill me-2"></i>

            <div>
                Estudiante registrado correctamente.
            </div>

        </div>

    {/if}

</div>


<Footer />


<style>

    .titulo {
        color: #0f3460;
    }


    .formulario-card,
    .estudiantes-card {
        border: none;
        border-radius: 18px;

        box-shadow:
            0 4px 15px rgba(15, 52, 96, 0.08);
    }


    .icono-formulario {

        width: 55px;
        height: 55px;

        border-radius: 13px;

        background-color: #eaf2fb;
        color: #0f3460;

        display: flex;
        align-items: center;
        justify-content: center;

        font-size: 1.5rem;

    }


    .form-control {

        border-radius: 10px;
        padding: 11px 13px;

    }


    .form-control:focus {

        border-color: #0f3460;

        box-shadow:
            0 0 0 0.2rem rgba(15, 52, 96, 0.1);

    }


    .btn-primary {

        background-color: #0f3460;
        border-color: #0f3460;

    }


    .btn-primary:hover {

        background-color: #0b294d;
        border-color: #0b294d;

    }


    .cantidad {

        width: 40px;
        height: 40px;

        border-radius: 50%;

        background-color: #eaf2fb;
        color: #0f3460;

        display: flex;
        align-items: center;
        justify-content: center;

        font-weight: bold;

    }


    .vacio {

        min-height: 300px;

        display: flex;
        flex-direction: column;

        align-items: center;
        justify-content: center;

        text-align: center;

    }


    .icono-vacio {

        width: 70px;
        height: 70px;

        border-radius: 50%;

        background-color: #eaf2fb;
        color: #0f3460;

        display: flex;
        align-items: center;
        justify-content: center;

        font-size: 1.8rem;

    }


    .avatar {

        width: 42px;
        height: 42px;

        border-radius: 50%;

        background-color: #eaf2fb;
        color: #0f3460;

        display: flex;
        align-items: center;
        justify-content: center;

    }


    thead {

        background-color: #f5f7fa;

    }


    th {

        color: #0f3460;
        font-size: .9rem;

    }


    td {

        color: #444;

    }


    .edad {

        background-color: #f1f5f9;

        padding: 6px 10px;

        border-radius: 8px;

        font-size: .9rem;

    }

</style>