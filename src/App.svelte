<script>
    let listIsOpen = true
    function openList() {
        listIsOpen = !listIsOpen
    }
    function productClick(num) {
        alert(num)
    }
    function customEvent() {
        let dataLayer = window.dataLayer || []
        dataLayer.push({
            event: 'custom_click',
            check_text: 'success',
        })
    }
</script>

<main>
    <h1>GTM測試用網頁</h1>
    <button id="listSwitch" on:click={openList}>Switch List</button>
    <button on:click={customEvent}>Custom Event</button>
    <div class="{listIsOpen ? 'open' : 'close'} product-list">
        <div class="product" id="item1" on:click={() => productClick(1)}>1</div>
        <div class="product" id="item2" on:click={() => productClick(2)}>2</div>
        <div class="product" id="item3" on:click={() => productClick(3)}>3</div>
        <div class="product" id="item4" on:click={() => productClick(4)}>4</div>
    </div>
</main>

<style>
    main {
        min-height: 90vh;
    }
    .product-list {
        height: 600px;
    }
    .product-list.close {
        height: 0;
        overflow: hidden;
    }
    .product {
        height: 100px;
        height: 100px;
        background: pink;
        margin: 50px;
    }
</style>
