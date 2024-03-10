
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
        { id: 1, src: image1, budget: "$$165 000 000" , fees: "$774 136 705", title: 'Интерстеллар', releaseDate: '2014',description: 'Когда засуха, пыльные бури и вымирание растений приводят человечество к продовольственному кризису, коллектив исследователей и учёных отправляется сквозь червоточину (которая предположительно соединяет области пространства-времени через большое расстояние) в путешествие, чтобы превзойти прежние ограничения для космических путешествий человека и найти планету с подходящими для человечества условиями', director: 'Кристофер Нолан',  Genre: 'фантастика, драма, приключения', country: 'США, Великобритания, Канада', AgeRating: '18+' },
        { id: 2, src: image2, budget: "$200 000 000" , fees: "$2 264 743 305", title: 'Титаник', releaseDate: '1997', description: 'В первом и последнем плавании шикарного «Титаника» встречаются двое. Пассажир нижней палубы Джек выиграл билет в карты, а богатая наследница Роза отправляется в Америку, чтобы выйти замуж по расчёту. Чувства молодых людей только успевают расцвести, и даже не классовые различия создадут испытания влюблённым, а айсберг, вставший на пути считавшегося непотопляемым лайнера.', director: 'Джеймс Кэмерон', Genre: 'драма, приключения, романтика', country: 'США, Великобритания', AgeRating: '12+' },
        {id: 3, src: image3, budget: "$11 000 000" , fees: "$503 015 849", title: 'Звёздные войны: Эпизод IV - Новая надежда', releaseDate: '1977', description: 'Татуин. Планета-пустыня. Уже постаревший рыцарь Джедай Оби Ван Кеноби спасает молодого Люка Скайуокера, когда тот пытается отыскать пропавшего дроида. С этого момента Люк осознает свое истинное назначение: он один из рыцарей Джедай. В то время как гражданская война охватила галактику, а войска повстанцев ведут бои против сил злого Императора, к Люку и Оби Вану присоединяется отчаянный пилот-наемник Хан Соло, и в сопровождении двух дроидов, R2D2 и C-3PO, этот необычный отряд отправляется на поиски предводителя повстанцев – принцессы Леи. Героям предстоит отчаянная схватка с устрашающим Дартом Вейдером – правой рукой Императора и его секретным оружием – «Звездой Смерти».', director: 'Джордж Лукас', Genre: 'фантастика, боевик, приключения', country: 'США', AgeRating: '12+'} ,
        { id: 4, src: image4, budget: "$25 000 000" , fees: "$$28 418 687", title: 'Побег из Шоушенка', releaseDate: '1994', description: 'Бухгалтер Энди Дюфрейн обвинён в убийстве собственной жены и её любовника. Оказавшись в тюрьме под названием Шоушенк, он сталкивается с жестокостью и беззаконием, царящими по обе стороны решётки. Каждый, кто попадает в эти стены, становится их рабом до конца жизни. Но Энди, обладающий живым умом и доброй душой, находит подход как к заключённым, так и к охранникам, добиваясь их особого к себе расположения.', director: 'Фрэнк Дарабонт', Genre: 'драма', country: 'США', AgeRating: '16+' },
        { id: 5, src: image5, budget: "$93 000 000" , fees: "$898 204 420", title: 'Властелин колец: Братство кольца', releaseDate: '2001', description: 'Тихая деревня, где живут хоббиты. Придя на 111-й день рождения к своему старому другу Бильбо Бэггинсу, волшебник Гэндальф начинает вести разговор о кольце, которое Бильбо нашел много лет назад. Это кольцо принадлежало когда-то темному властителю Средиземья Саурону, и оно дает большую власть своему обладателю. Теперь Саурон хочет вернуть себе власть над Средиземьем. Бильбо отдает Кольцо племяннику Фродо, чтобы тот отнёс его к Роковой Горе и уничтожил.', director: 'Питер Джексон', Genre: 'фэнтези, приключения', country: 'Новая Зеландия, США', AgeRating: '12+' },
        { id: 6, src: image6, budget: "$125 000 000" , fees: "$974 755 371", title: 'Гарри Поттер и философский камень', releaseDate: '2001', description: 'Жизнь десятилетнего Гарри Поттера нельзя назвать сладкой: родители умерли, едва ему исполнился год, а от дяди и тёти, взявших сироту на воспитание, достаются лишь тычки да подзатыльники. Но в одиннадцатый день рождения Гарри всё меняется. Странный гость, неожиданно появившийся на пороге, приносит письмо, из которого мальчик узнаёт, что на самом деле он - волшебник и зачислен в школу магии под названием Хогвартс. А уже через пару недель Гарри будет мчаться в поезде Хогвартс-экспресс навстречу новой жизни, где его ждут невероятные приключения, верные друзья и самое главное — ключ к разгадке тайны смерти его родителей.', director: 'Крис Коламбус', Genre: 'фэнтези, приключения', country: 'Великобритания, США', AgeRating: '6+' },
        { id: 7, src: image7, budget: "$14 000 000" , fees: "$233 555 708", title: 'Игра в имитацию', releaseDate: '2014', description: 'Гениальный математик Алан Тьюринг — фигура, чью роль в ходе Второй мировой войны сложно переоценить. Он стал тем человеком, который взломал код немецкой шифровальной машины «Энигма», таким образом приблизив поражение противника.', director: 'Рон Ховард', Genre: 'драма, биография', country: 'США', AgeRating: '12+' },
        { id: 8, src: image8, budget: "$1 200 000" , fees: "$25 100 000", title: 'Хороший, плохой, злой', releaseDate: '1966', description: 'Разгар Гражданской войны, Дикий Запад. По воле судьбы трое мужчин вынуждены объединить усилия в поисках украденного золота. Но совместная работа — не самое подходящее занятие для таких отъявленных бандитов. Компаньоны вскоре понимают, что в их дерзком и опасном путешествии по разоренной войной стране самое важное — никому не доверять и держать пистолет наготове.', director: 'Серджио Леоне', Genre: 'вестерн', country: 'Италия, Испания, Германия, США', AgeRating: '16+' },
        { id: 9, src: image9, budget: "$237 000 000" , fees: "$2 923 905 528", title: 'Аватар', releaseDate: '2009', description: 'Бывший морпех Джейк Салли прикован к инвалидному креслу. Несмотря на немощное тело, Джейк в душе по-прежнему остается воином. Он получает задание совершить путешествие в несколько световых лет к базе землян на планете Пандора, где корпорации добывают редкий минерал, имеющий огромное значение для выхода Земли из энергетического кризиса.', director: 'Джеймс Кэмерон', Genre: 'фантастика, боевик, приключения', country: 'США, Великобритания', AgeRating: '12+' },
        { id: 10, src: image10, budget: "$220 000 000" , fees: "$1 518 812 988", title: 'Мстители', releaseDate: '2012', description: 'Локи, сводный брат Тора, возвращается, и в этот раз он не один. Земля оказывается на грани порабощения, и только лучшие из лучших могут спасти человечество. Глава международной организации Щ.И.Т. Ник Фьюри собирает выдающихся поборников справедливости и добра, чтобы отразить атаку. Под предводительством Капитана Америки Железный Человек, Тор, Невероятный Халк, Соколиный Глаз и Чёрная Вдова вступают в войну с захватчиком.', director: 'Джосс Уидон', Genre: 'фантастика, боевик, приключения', country: 'США', AgeRating: '12+' },
        { id: 11, src: image11, budget: "$19 185 746" , fees: "$19 552 639", title: 'Леон', releaseDate: '1994', description: 'Профессиональный убийца Леон неожиданно для себя самого решает помочь 12-летней соседке Матильде, семью которой убили коррумпированные полицейские.', director: 'Люк Бессон', Genre: 'боевик, драма, криминал', country: 'Франция', AgeRating: '18+' },
        { id: 12, src: image12, budget: "-" , fees: "-", title: 'Бриллиантовая рука', releaseDate: '1968', description: 'В южном городке орудует шайка валютчиков, возглавляемая Шефом и его помощником Графом (в быту — Геной Козодоевым). Скромный советский служащий и примерный семьянин Семен Семенович Горбунков отправляется в зарубежный круиз на теплоходе, где также плывет Граф, который должен забрать бриллианты в одном из восточных городов и провезти их в загипсованной руке. Но из-за недоразумения вместо жулика на условленном месте падает ничего не подозревающий Семен Семенович, и драгоценный гипс накладывают ему.', director: 'Леонид Гайдай', Genre: 'комедия, криминал', country: 'СССР', AgeRating: '18+'}
    
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