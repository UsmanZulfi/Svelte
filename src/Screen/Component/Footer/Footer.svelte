<script>
    import footer_icon from "../../../Assets/Images/Logo.png";
</script>

<div>
    <div class="footer_orange">
        <p>©2023 Genesis FS Card Services Inc. All Rights Reserved.</p>
    </div>
    <div class="footer">
        <img class="image" src={footer_icon} alt="" />
        <p class="text">
            Destiny is a registered trademark of Genesis FS Card Services, Inc.
            The Destiny Mastercard is issued by First Electronic Bank, Member
            FDIC, and serviced by Genesis FS Card Services, Inc. (NMLS #1549514)
            14600 Greenbrier Parkway, Beaverton, OR 97006
        </p>
    </div>
</div>

<style>
    .text{
        width: 50%;
        padding-top: 42px;
        font-family: "Arial";
        font-style: normal;
        font-weight: 400;
        font-size: 16px;
        line-height: 18px;
        text-align: center;
    }
    .footer {
        padding-top: 62px;
        display: flex;
        flex-direction: column;
        background-color: #0b1c57;
        color: white;
        align-items: center;
        text-align:center;
    }
    .footer_orange {
        height: 41px;
        width: 100%;
        background-color: #dd5327;
        color: #ffffff;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .image{
        display: flex;
        width: 30%;
    }
    p {
        font-family: "Arial";
        font-style: normal;
        font-weight: 400;
        font-size: 16px;
        line-height: 18px;
        text-align: center;
    }
    @media (max-width: 768px) {
        p {
            font-family: "Arial";
            font-style: normal;
            font-weight: 400;
            font-size: 12px;
            line-height: 18px;
            text-align: center;
        }
        .footer {
        padding-top: 30px;
        /* display: flex;
        flex-direction: column;
        height: 200px;
        background-color: #0b1c57;
        color: white;
        align-items: center;
        text-align:center; */
    }
    .text{
        width: 80%;
        padding-top: 12px;
        font-family: "Arial";
        font-style: normal;
        font-weight: 500;
        font-size: 12px;
        line-height: 18px;
        text-align: center;
    }
    }
</style>
