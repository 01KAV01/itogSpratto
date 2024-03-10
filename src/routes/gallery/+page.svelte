
<div class="gallery">
    {#each images as image (image.id)}
        <img src={image.src} alt="Project" on:mouseenter={() => image.scale = 1.1} on:mouseleave={() => image.scale = 1} on:click={() => openModal(image)} >
    {/each}
</div>
{#if showModal}
    <div class="modal" on:click={() => closeModal()}>
        <div class="modal-content" on:click|stopPropagation>
            <img src={selectedImage.src} alt="Project" style="width: 100%;">
        </div>
    </div>
{/if}



<script>
    import image1 from '../../image/1.jpg';
    import image2 from '../../image/2.jpg';
    import image3 from '../../image/3.jpg';
    import image4 from '../../image/4.jfif';
    import image5 from '../../image/5.jpeg';
    import image6 from '../../image/6.jpg';
    import image7 from '../../image/7.jpg';
    import image8 from '../../image/8.jpg';
    import image9 from '../../image/9.jpg';
    import image10 from '../../image/10.jpg';
    import image11 from '../../image/11.jpg';
    import image12 from '../../image/12.jpg';



    let images = [
        { id: 1, src: image1 },
        { id: 2, src: image2 },
        { id: 3, src: image3 },
        { id: 4, src: image4 },
        { id: 5, src: image5 },
        { id: 6, src: image6 },
        { id: 7, src: image7 },
        { id: 8, src: image8 },
        { id: 9, src: image9 },
        { id: 10, src: image10 },
        { id: 11, src: image11 },
        { id: 12, src: image12 },
    
    ];

    let showModal = false;
    let selectedImage = null;

    function openModal(image) {
        selectedImage = image;
        showModal = true;
    }

    function closeModal() {
        showModal = false;
    }

</script>

<style>
.gallery {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
}

.gallery img {
    width: 600px;
    height: 600px;
    object-fit: cover;
    cursor: pointer;
    transform: scale(1);
    transition: transform 0.45s;
}

.gallery img:hover {
    transform: scale(1.035);
    transition: transform 0.45s;
}

.modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
}

.modal-content {
    background-color: white;
    padding: 20px;
    max-width: 90%;
    max-height: 90%;
    overflow: auto;
}

.close-button {
    position: absolute;
    top: 10px;
    right: 10px;
    background-color: transparent;
    border: none;
    cursor: pointer;
}

    </style>