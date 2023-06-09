<script>
    import Footer from "../Footer/Footer.svelte";
    import user_profile from "../../../Assets/Images/amir.jpg";
    import usama from "../../../Assets/Images/usama.jpg";
    import usman from "../../../Assets/Images/usman_bhai.jpg";
    import haris from "../../../Assets/Images/haris.jpg";
    const customer_review = [
        {
            user_name: "Amir Ali",
            image: user_profile,
            review: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo c",
        },
        {
            user_name: "Usman Zulfiqar",
            image: usman,
            review: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo c",
        },
        {
            user_name: "Usama Bin Tahir",
            image: usama,
            review: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo c",
        },
        {
            user_name: "Haris Saleem",
            image: haris,
            review: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo c",
        },
    ];
</script>

<div class="main">
    <h1>What our clients said about us</h1>
    <div class="main_div">
        {#each customer_review as review (review)}
            <div class="card_div">
                <div class="card">
                    <div class="image_div">
                        <img class="user_image" src={review?.image} alt="a12" />
                    </div>
                    <h3 class="card_user_name">{review?.user_name}</h3>

                    <p>
                        {review?.review}
                    </p>
                </div>
            </div>
        {/each}
    </div>
    <Footer />
</div>

<style>
    .main {
        display: flex;
        flex-direction: column;
        background-color: white;
    }
    .main_div {
        display: flex;
        flex-direction: row;
        overflow-x: auto;
    }
    .main_div::-webkit-scrollbar {
        display: none;
    }
    h1 {
        padding-top: 32px;
        margin-left: 65px;
        font-family: "Arial";
        font-style: normal;
        font-weight: 700;
        font-size: 32px;
        line-height: 37px;
        color: #5f3fc6;
    }
    .card_div {
        display: flex;
    }
    .image_div {
        position: absolute;
        left: 2%;
        margin-top: -80px;
    }
    .card {
        margin-top: 80px;
        position: relative;
        margin-left: 31px;
        padding-left: 45px;
        width: 573px;
        height: 235px;
        background: #ffffff;
        box-shadow: 4px 4px 15px 1px rgba(99, 87, 255, 0.19);
        border-radius: 22px;
        margin-bottom: 87px;
        display: flex;
        flex-direction: column;
    }
    .card_user_name {
        padding-left: 150px;
    }
    .user_image {
        box-sizing: border-box;
        width: 144px;
        height: 144px;
        border: 4px solid #5f3fc6;
        border-radius: 50%;
        /* position: absolute;
        left: 4%;
        top: 200%; */
        margin-bottom: 50px;
    }

    @media (max-width: 768px) {
        h1 {
            background: linear-gradient(180deg, #6357ff 0%, #91b4f9 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            font-family: "Arial";
            font-style: normal;
            font-weight: 700;
            font-size: 20px;
            line-height: 23px;
            padding-left: 0;
            margin-left: 0px;
            text-align: center;
        }
        .card {
            margin-left: 12px;
            padding-left: 45px;
            width: 289px;
            height: 200px;
            background: #ffffff;
            box-shadow: 4px 4px 15px 1px rgba(99, 87, 255, 0.19);
            border-radius: 22px;
            margin-bottom: 87px;
            display: flex;
            flex-direction: column;
        }
        .card_user_name {
            padding-left: 0px;
            text-align: center;
        }
        .user_image {
            box-sizing: border-box;
            width: 101px;
            height: 101px;
            border: 4px solid #5f3fc6;
            border-radius: 50%;
            margin-bottom: 50px;
        }
        p {
            margin: 0px;
        }
    }
    /* @media (max-width: 600px) {
        .card {
            margin-left: 12px;
            padding-left: 21px;
            padding-right: 21px;
            width: 70%;
            height: 252px;
            background: #ffffff;
            box-shadow: 4px 4px 15px 1px rgba(99, 87, 255, 0.19);
            border-radius: 22px;
            margin-bottom: 87px;
            display: flex;
            flex-direction: column;
        }
        .user_image {
            box-sizing: border-box;
            width: 101px;
            height: 101px;
            border: 4px solid #5f3fc6;
            border-radius: 50%;
            margin-bottom: 50px;
        }
    } */
</style>
