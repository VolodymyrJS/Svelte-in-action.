<script>
    import Header from './MeetUps/Header.svelte';
    import Footer from './MeetUps/Footer.svelte';
</script>

<style>

    .Site {
        display: flex;
        min-height: 100vh;
        flex-direction: column;
    }

    .site-content {
        align-self: center;
        margin-top: 80px;
        flex: 1;
        justify-items: center;
        justify-content: center;
    }

</style>

<body class="Site">
    <Header />
    <div class="site-content">Main content</div>
    <Footer />
</body>


