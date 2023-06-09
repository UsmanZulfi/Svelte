<script>
    // export let name;
    import image from "../../Assets/Images/Logo.png";
    import girl_logo from "../../Assets/Images/girl_logo.png";
    import { onMount, onDestroy } from "svelte";
    // import cloud_icon from "../../Assets/SVG/cloud_lock.svg";
    import Button from "../Component/Button/Button.svelte";
    import Slider from "../Component/slider/slider.svelte";
    import Footer from "../Component/Footer/Footer.svelte";
    import { navigate } from "svelte-navigator";
    import Modal from "./Modal.svelte";
    let isMobile = false;

    let showModal = false;
    const checkScreenWidth = () => {
        isMobile = window.innerWidth < 600;
    };

    onMount(() => {
        checkScreenWidth();
        window.addEventListener("resize", checkScreenWidth);
    });

    onDestroy(() => {
        window.removeEventListener("resize", checkScreenWidth);
    });
    let showPopup = false;

    const onShowPopup = (ev) => {
        showPopup = true;
    };

    const onPopupClose = (data) => {
        showPopup = false;

        console.log(data);
    };
</script>

<div class="Main_page">
    <header><img class="logo" src={image} alt="adj" /></header>
    <div class="first_div">
        <div class="main">
            <p>Get the best of both worlds now!</p>
        </div>
        <div class="main_for_margin">
            <div class="center_main">
                <div class="image_wrapper">
                    <img src={girl_logo} class="image" alt="asjd" />
                </div>
            </div>
        </div>
        <div class="text-box">
            <h1>
                {#if isMobile}
                    <h4>
                        Your hassle-free solution to many financial challenges
                        is Destiny Mastercard® - an unsecured credit card
                    </h4>
                    <ul>
                        <li>Helps you build your credit</li>
                        <li>Provides freedom of using a credit card</li>
                        <li>Carries no burden of a security deposit</li>
                    </ul>
                {:else}
                    <h3>
                        Your hassle-free solution to many financial challenges
                        is Destiny Mastercard®
                    </h3>
                {/if}
            </h1>
            <button class="try_now" on:click={() => (showModal = true)}>Try it now</button>
            <Modal bind:showModal>
                <h2 slot="header" class="modal_heading">
                    DESTINY
                    
                </h2>
            
                <ol class="definition-list">
                    <li>A CARD THAT NEXT LEVEL OF THE REVOLUTION</li>
                    <li>
                        STAY TUNNED
                    </li> 
                </ol>
            </Modal>
        </div>

        <Button />
    </div>
    <Slider />
</div>

<style>
    header {
        background-color: #5f3fc6;
        border-color: #5f3fc6;
    }
    .logo {
        height: 50px;
        width: 400px;
    }
    .definition-list{
        color: #ffffff;
    }
    .first_div {
        background-color: #5f3fc6;
    }
    .text-box {
        margin-top: 20px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        text-align: center;
    }
    .try_now {
        width: 323px;
        height: 66px;
        background: #dd5327;
        box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.25);
        border-radius: 14px;
        border-color: transparent;
        font-family: "Arial";
        font-style: normal;
        font-weight: 700;
        font-size: 20px;
        line-height: 23px;
        color: #ffffff;
        /* Responsive styles */
        @media (max-width: 600px) {
            width: 90%;
            max-width: 400px;
            height: 56px;
            font-size: 16px;
            line-height: 20px;
        }
    }
    .modal_heading{
        color: #ffffff;
    }
    h1 {
        color: white;
        font-family: Arial, Helvetica, sans-serif;
        width: 50%;
        height: 199px;
        background: rgba(255, 255, 255, 0.13);
        box-shadow: 0px 4px 11px rgba(0, 0, 0, 0.25);
        border-radius: 39px;
    }
    h4 {
        font-family: Arial;
        font-size: 16px;
        font-weight: 700;
        line-height: 18px;
        letter-spacing: 0em;
        text-align: center;
    }
    li {
        font-family: Arial;
        font-size: 14px;
        font-weight: 400;
        line-height: 16px;
        letter-spacing: 0em;
        text-align: left;
    }
    header {
        display: flex;
        padding-top: 40px;
        justify-content: center;
    }
    .main {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        margin: 0;
    }
    p {
        text-align: center;
        color: white;
        font-family: Arial, Helvetica, sans-serif;
        font-size: 64px;
        font-weight: 700;
        width: 700px;
        height: 148px;
        /* Responsive styles */
        @media (max-width: 768px) {
            width: 90%;
            font-size: 48px;
        }
    }
    .center_main {
        margin-top: 140px;
        position: relative;
        height: 20vh;
        width: 100%;
        background-color: rgb(219, 80, 21);
        display: flex;
        justify-content: center;
        align-items: center;
        margin-bottom: 150px;
    }
    .image {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        /* max-width: 100%; */
        height: 400px;
        width: 400px;
        /* max-height: 400px; */
    }
    .image_wrapper {
        position: relative;
        /* width: 100%; */
        padding-bottom: 100%;
    }
    @media (max-width: 990px) {
        header {
            background-color: #5f3fc6;
            border-color: transparent;
        }
        h3 {
            font-size: 24px;
        }
        h1 {
            color: white;
            font-family: Arial, Helvetica, sans-serif;
            width: 57%;
            height: 129px;
            background: rgba(255, 255, 255, 0.13);
            box-shadow: 0px 4px 11px rgba(0, 0, 0, 0.25);
            border-radius: 39px;
        }
    }
    @media (max-width: 600px) {
        header {
            background-color: #5f3fc6;
            border-color: #5f3fc6;
        }
        .logo {
            height: 40px;
            width: 400px;
        }
        .logo {
            width: 50%;
            max-width: 300px;
        }
        .text-box {
            /* margin-top: 100px; */
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
        }
        h1 {
            color: white;
            font-family: Arial, Helvetica, sans-serif;
            width: 90%;
            height: 223px;
            background: rgba(255, 255, 255, 0.13);
            box-shadow: 0px 4px 11px rgba(0, 0, 0, 0.25);
            border-radius: 39px;
        }
        h3 {
            font-size: 20px;
            height: auto;
        }
        p {
            text-align: center;
            color: white;
            font-family: Arial, Helvetica, sans-serif;
            font-size: 64px;
            font-weight: 700;
            /* height: 148px; */
            margin-bottom: 20px;

            /* Responsive styles */

            width: 90%;
            font-size: 48px;
        }
        .image {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            /* max-width: 100%; */
            width: 204px;
            max-height: 210px;
            /* max-height: 400px; */
        }
        .text-box {
            margin-top: 40px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
        }
        .center_main {
            margin-top: 130px;
            position: relative;
            height: 12vh;
            width: 100%;
            background-color: rgb(219, 80, 21);
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 80px;
        }
    }
</style>
