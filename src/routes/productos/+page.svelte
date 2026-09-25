<script>
    import Navbar from '$lib/components/navbar.svelte';
    import Footer from '$lib/components/footer.svelte';
    import Header from '$lib/components/header.svelte';
    let productos = [
        {
            titulo: 'Artículo científico sobre IA',
            tipo: 'Artículo',
            proyecto: 'Sistema inteligente de residuos',
            fecha: '2026'
        },
        {
            titulo: 'Ponencia Feria de Investigación',
            tipo: 'Ponencia',
            proyecto: 'Sistema de gestión académica',
            fecha: '2026'
        },
        {
            titulo: 'Prototipo de sistema web',
            tipo: 'Prototipo',
            proyecto: 'Sistema de gestión académica',
            fecha: '2026'
        }
    ];
</script>

<Navbar />

<div class="container py-5">

    <div class="d-flex justify-content-between align-items-center mb-4">

        <div>
            <h1 class="fw-bold titulo">
                Productos de investigación
            </h1>

            <p class="text-secondary">
                Consulta los productos generados por los proyectos.
            </p>
        </div>

        <button class="btn btn-primary">
            <i class="bi bi-plus-lg me-2"></i>
            Registrar producto
        </button>

    </div>


    <div class="row g-4">

        {#each productos as producto}

            <div class="col-12 col-md-6 col-xl-4">

                <div class="card producto-card h-100">

                    <div class="card-body p-4">

                        <div class="icono mb-4">
                            <i class="bi bi-file-earmark-text"></i>
                        </div>

                        <span class="badge bg-primary-subtle text-primary mb-3">
                            {producto.tipo}
                        </span>

                        <h4 class="fw-bold">
                            {producto.titulo}
                        </h4>

                        <p class="text-secondary">
                            Proyecto:
                            <strong>
                                {producto.proyecto}
                            </strong>
                        </p>

                        <div class="d-flex justify-content-between align-items-center mt-4">

                            <small class="text-secondary">
                                Año {producto.fecha}
                            </small>

                            <button class="btn btn-outline-primary btn-sm">
                                Ver producto
                            </button>

                        </div>

                    </div>

                </div>

            </div>

        {/each}

    </div>

</div>


<style>
    .titulo {
        color: #0f3460;
    }

    .producto-card {
        border: none;
        border-radius: 18px;
        box-shadow: 0 4px 15px rgba(15,52,96,.08);
        transition: .2s;
    }

    .producto-card:hover {
        transform: translateY(-4px);
    }

    .icono {
        width: 55px;
        height: 55px;
        border-radius: 13px;

        background: #eaf2fb;
        color: #0f3460;

        display: flex;
        align-items: center;
        justify-content: center;

        font-size: 1.5rem;
    }
</style>