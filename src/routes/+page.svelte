
<div class="gallery">
    {#each images as image (image.id)}
    <div class="image-container" style="transform: scale({image.scale});">
        <img src={image.src} alt={image.title}  on:click={() => openModal(image)}>
        <div class="overlay-text">{image.title}</div>
    </div>
    {/each}
</div>
{#if showModal}
 <!-- svelte-ignore a11y-no-static-element-interactions -->
 <!-- svelte-ignore a11y-click-events-have-key-events -->
 <div class="modal" on:click={() => closeModal()}>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div class="modal-content" on:click|stopPropagation>
        <div class="parentBox" > 
            <h2>{selectedImage.title}</h2>
            <div class="box">
                <div class="childeBox1"><img src={selectedImage.src} alt="Project" style="width: 100%;"></div>
                <div class="childeBox2">
                     <p>Дата выпуска: {selectedImage.releaseDate}</p>
                    <p>Режиссер: {selectedImage.director}</p>
                    <p>Жанр: {selectedImage.Genre}</p>
                    <p>Страна: {selectedImage.country}</p>
                    <p>Возрастное ограничение: {selectedImage.AgeRating}</p>
                    <p>Бюджет: {selectedImage.budget}</p>
                    <p>Сборы: {selectedImage.fees}</p>
                </div>
            </div>
            <div class="image-description"> <p>{selectedImage.description}</p></div>
        </div>


            <div class="box">
                <button class="buy-ticket-button">Купить билет</button>
                <button class="buy-ticket-button">Добавить в закладки</button>
            </div>
    </div>
</div>
   
 
{/if}



<script>
    import image1 from '../image/1.jpg';
    import image2 from '../image/2.jpg';
    import image3 from '../image/3.jpg';
    import image4 from '../image/4.jpg';
    import image5 from '../image/5.jpg';
    import image6 from '../image/6.jpg';
    import image7 from '../image/7.jpg';
    import image8 from '../image/8.jpg';
    import image9 from '../image/9.jpg';
    import image10 from '../image/10.jpg';
    import image11 from '../image/11.jpg';
    import image12 from '../image/12.jpg';




    let images = [
        { id: 1, src: image1, budget: "$150 000 000" , fees: "$585 349 010", title: 'Я – легенда', releaseDate: '2007',description: 'Адаптация одноименного романа Ричарда Мэтисона о неизвестном вирусе, унесшем жизни половины населения земного шара, а остальную половину превратившего в вампиров. Сюжет строится вокруг единственного уцелевшего человека с необъяснимым иммунитетом, ночами держащего бесконечную осаду упырей, а днем пытающегося найти противоядие и выяснить причины эпидемии.', director: 'Фрэнсис Лоуренс',  Genre: 'Боевик/Научная фантастика', country: 'США, Великобритания, Канада', AgeRating: '13+' },
        { id: 2, src: image2, budget: "$120 000 000" , fees: "$347 198 023", title: 'Я, робот', releaseDate: '2004', description: 'Действие фильма происходит в будущем (2035 г.), где роботы являются обычными помощниками человека. Главный герой — полицейский, «не переваривающий» роботов, расследует дело об убийстве, в которое оказывается вовлечен робот.', director: 'Алекс Пройас', Genre: 'Фантастика, Боевики, Триллеры', country: 'США, Великобритания', AgeRating: '12+' },
        {id: 3, src: image3, budget: "$110 000 000" , fees: "$299 268 508", title: 'Живая сталь', releaseDate: '2011', description: 'События фильма происходят в будущем, где бокс запрещен за негуманностью и заменен боями 2000-фунтовых роботов, управляемых людьми. Бывший боксер, а теперь промоутер, переметнувшийся в Робобокс, решает, что наконец нашел своего чемпиона, когда ему попадается выбракованный, но очень способный робот. ', director: 'Шон Леви', Genre: 'фантастика, боевик', country: 'США, Индия', AgeRating: '13+'} ,
        { id: 4, src: image4, budget: "$140 000 000" , fees: "$585 796 247", title: 'Железный человек', releaseDate: '2008', description: 'Миллиардер-изобретатель Тони Старк попадает в плен к Афганским террористам, которые пытаются заставить его создать оружие массового поражения. В тайне от своих захватчиков Старк конструирует высокотехнологичную киберброню, которая помогает ему сбежать. Однако по возвращении в США он узнаёт, что в совете директоров его фирмы плетётся заговор, чреватый страшными последствиями. Используя своё последнее изобретение, Старк пытается решить проблемы своей компании радикально.', director: 'Джон Фавро', Genre: 'научная фантастика, боевик', country: 'США', AgeRating: '13+' },
        { id: 5, src: image5, budget: "$190 000 000" , fees: "$411 002 906", title: 'Тихоокеанский рубеж', releaseDate: '2013', description: 'Когда из морских глубин поднялись легионы чудовищ, известных как Кайдзу, началась война, которой суждено было забрать миллионы жизней и свести «человеческие ресурсы» почти к нулю всего за несколько лет. Чтобы сражаться с пришельцами, было создано специальное оружие: огромные роботы, названные Джегерами, они управлялись одновременно двумя пилотами, чьи сознания соединены с помощью нейронной связи. Но даже Джегеры оказываются почти бессильны перед лицом безжалостных Кайдзу. На грани поражения у защитников человечества нет выбора, кроме как обратиться к двум весьма сомнительным героям — никому не нужному бывшему пилоту и неопытному стажеру — которые объединились, чтобы повести в бой некогда легендарного, но сейчас устаревшего Джегера. Вместе они оказываются единственной надеждой человечества, последним препятствием перед надвигающимся апокалипсисом.', director: 'Гильермо дель Торо', Genre: 'фантастика, приключения, боевик', country: 'США, Мексика', AgeRating: '12+' },
        { id: 6, src: image6, budget: "$32 500 000" , fees: "$475 106 177", title: 'Звёздные войны. Эпизод VI: Возвращение джедая', releaseDate: '1983', description: 'В заключительном шестом эпизоде «Звездных войн» Дарт Вейдер создает вторую «Звезду Смерти». Он объединяет все силы зла, чтобы с помощью этого смертоносного оружия нанести последний сокрушительный удар по повстанцам и их союзникам.', director: ' Джордж Лукас', Genre: 'фэнтези, приключения', country: 'США', AgeRating: '12+' },
        { id: 7, src: image7, budget: "$100 000 000" , fees: "$230 884 728", title: 'Константин: Повелитель тьмы', releaseDate: '2005', description: 'Джону Константину удалось не только побывать в аду, но и вернуться обратно. Родившись с неугодным самому себе талантом — способностью распознавать помесь ангелов и демонов, которые бродят по земле в облике людей, — Константин под давлением обстоятельств пытается совершить самоубийство, лишь бы избавиться от мучительных видений. Но неудачно. Воскрешенный против собственной воли он снова оказывается в мире живых. Теперь, отмеченный печатью суицида и получивший временное право на жизнь, он патрулирует границу, разделяющую рай и ад, тщетно надеясь на обретение спасения путем сражения с земными ставленниками зла.', director: 'Фрэнсис Лоуренс', Genre: 'Фэнтези, Триллеры, Драмы', country: 'США', AgeRating: '18+' },
        { id: 8, src: image8, budget: "$80 000 000" , fees: "$164 115 897", title: 'Розовая пантера', releaseDate: '2006', description: 'Шах вымышленного ближневосточного государства Лугаша дарит своей единственной дочери, принцессе Дале, самый большой алмаз в мире — «Розовую Пантеру». Когда Дала вырастает, в Лугаше происходит революция, но принцесса успевает взять с собой алмаз, отправляясь в изгнание в Европу. Там вокруг принцессы, а точнее алмаза, водят хоровод английский аристократ сэр Чарльз Литтон, его племянник Джордж и французский инспектор Жак Клузо. Такая комбинация, как и положено, приводит к феерической кульминации и неожиданному финалу.', director: 'Блейк Эдвардс', Genre: '	Комедия, Криминальный', country: 'Италия, Испания, Германия, Франция, США', AgeRating: '0+' },
        { id: 9, src: image9, budget: "$60 000 000" , fees: "$286 801 374", title: 'Зелёная миля', releaseDate: '1999', description: 'Обвиненный в страшном преступлении, Джон Коффи оказывается в блоке смертников тюрьмы «Холодная гора». Вновь прибывший обладал поразительным ростом и был пугающе спокоен, что, впрочем, никак не влияло на отношение к нему начальника блока Пола Эджкомба, привыкшего исполнять приговор.', director: 'Фрэнк Дарабонт', Genre: '	фэнтезийная драма', country: 'США', AgeRating: '14+' },
        { id: 10, src: image10, budget: "$75 000 000" , fees: "$343 572 420", title: 'Иллюзия обмана', releaseDate: '2013', description: 'Команда лучших иллюзионистов мира проворачивает дерзкие ограбления прямо во время своих шоу, играя в кошки-мышки с агентами ФБР.', director: 'Луи Летерье', Genre: 'Триллер, Криминальный', country: 'США', AgeRating: '16+' },
        { id: 11, src: image11, budget: "$140 000 000" , fees: "$305 413 918", title: 'Пираты Карибского моря: Проклятие Черной жемчужины', releaseDate: '2003', description: 'Жизнь харизматичного авантюриста, капитана Джека Воробья, полная увлекательных приключений, резко меняется, когда его заклятый враг — капитан Барбосса — похищает корабль Джека, Черную Жемчужину, а затем нападает на Порт Ройал и крадет прекрасную дочь губернатора, Элизабет Свонн.', director: 'Гор Вербински', Genre: 'приключения, фэнтези, боевик, комедия', country: 'США', AgeRating: '13+' },
        { id: 12, src: image12, budget: "28 500 000" , fees: "54 000 000 ", title: 'Лекарь: Ученик Авиценны', releaseDate: '2013', description: 'Англия, XI век. Мать десятилетнего Роба Коула умирает в страшных мучениях: никто не знает ни природы её болезни, ни лекарства против неё. Маленький Роб, потрясенный до глубины души, во что бы то ни стало стремится разгадать эту тайну.', director: 'Филипп Штёльцль', Genre: '	Драма, приключения', country: 'Германия', AgeRating: '12+'}
    
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

 .image-description{
    max-width: 600px; 
    margin: 20px auto; 
    padding: 20px; 
    background-color: #f9f9f9; 
    border-radius: 10px; 
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); 
    font-family: 'Arial', sans-serif; 
    font-size: 16px; 
    line-height: 1.6; 
    color: #333; 
    text-align: justify; 
    }
.parentBox{
    width: 500px;
}
.childeBox1
{
    display: flex;
    min-width: 200px; 
    height: auto; 
    justify-content: center; 
    align-items: center; 
    background-color: #f9f9f9; 

}
.childeBox2
{
    
    min-width: 300px;
    height: auto;
    line-height: 230%;
    padding: 10px; 
    background-color: #f9f9f9; 

}
.childeBox1 img
{
    min-width: 200px; 

}
.box {
    display: flex;
    justify-content: space-between; 
    margin-top: 20px;
}
.image-container {
    position: relative;
    display: inline-block;
    margin: 10px; 
    margin: 10px; 
    overflow: hidden; 
 }

 .image-container img {
    width: 100%;
    height: auto;
    transition: transform 0.3s ease;
 }

 .image-container .overlay-text {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    background-color: rgba(0, 0, 0, 0.5); 
    font-size: 20px; 
    opacity: 0; 
    pointer-events: none; 
    transition: transform 0.3s ease;
 }

 .image-container:hover .overlay-text {
    opacity: 1; 
 }
.modal-content img{
    max-width: 35%;
    height: 400px;
}
.gallery {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
}

.gallery img {
    width: 400px;
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

.buy-ticket-button {

    display: inline-block;
 padding: 10px 20px;
 font-size: 16px;
 font-weight: bold;
 color: #ffffff;
 background-color: #007bff;
 border: none;
 border-radius: 5px;
 cursor: pointer;
 transition: background-color 0.3s ease;
}
.buy-ticket-button:hover {
 background-color: #0056b3;
}
.buy-ticket-button:active {
 background-color: #003d88;
 box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}


    </style>