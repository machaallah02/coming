<template>
    <div class="h-screen flex flex-col">
        <header class="flex justify-center items-center h-1/4 bg-cover bg-center bg-no-repeat"
            :style="{ backgroundImage: 'url(backimgs.jpg)' }">
            <img src="../assets/AFROSTD.png" alt="Logo Afro Stand" class="w-32 h-auto md:w-40 lg:w-48 m-4">
        </header>

        <main class="flex flex-col items-center text-black flex-grow p-4 md:p-8">
            <section class="w-full sm:w-3/4 lg:w-1/2 text-center margingC1 flex-grow">
                <p class="text-4xl sm:text-3xl md:text-6xl font-bold font1 mt-4">
                    Coming Soon ...
                </p>
                <p class="text-lg sm:text-xl md:text-2xl margingC">
                    Nous sommes heureux de vous informer que le site AfroStand sera bientôt en ligne ! Nous avons
                    consacré
                    beaucoup d'efforts pour développer une plateforme qui répond à vos attentes et qui vous offre une
                    expérience utilisateur optimale.
                </p>

                <div class="text-orange-400 margingC">
                    <span class="font1 text-8xl sm:text-4xl md:text-3xl lg:text-6xl font-bold" id="chrono">-- : -- : --
                        :--</span>
                </div>
                <div class="p-2 items-center justify-center text-center margingC">
                    <a href="https://wa.me/+22891067254?text=Bonjour, j'aimerais des informations sur Afro Stand."
                        class="bg-orange-950 text-orange-400 py-2 px-4 rounded mx-2 block sm:inline-block text-lg sm:text-xl md:text-2xl lg:text-3xl"
                        target="_blank">Contactez-nous</a>
                    <a href="#en-savoir-plus"
                        class="bg-orange-950 text-orange-400 py-2 px-4 mt-1 rounded mx-2 block sm:inline-block text-lg sm:text-xl md:text-2xl lg:text-3xl">En
                        savoir plus</a>
                </div>

            </section>
        </main>
    </div>
</template>

<script>
export default {
    name: 'ComingSoon',
    mounted() {
        const targetDate = new Date("November 20, 2024 00:00:00").getTime();

        const countdownInterval = setInterval(function () {

            const now = new Date().getTime();

            const distance = targetDate - now;

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("chrono").innerHTML = days + " : " + hours + " : " + minutes + " : " + seconds;

            if (distance < 0) {
                clearInterval(countdownInterval);
                document.getElementById("chrono").innerHTML = "EXPIRED";
            }
        }, 1000);
    }
}
</script>

<style scoped>
header {
    background-image: url('../assets/backimgs.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
}

.margingC {
    margin-top: 50px;
    margin-left: 0px;
    margin-right: 0px;
    margin-bottom: 20px;
}

.margingC1 {
    margin-top: 20px;
    margin-left: 40px;
    margin-right: 40px;
    margin-bottom: 20px;
}

.font1 {
    font-family: 'Krona One', sans-serif;
}
</style>