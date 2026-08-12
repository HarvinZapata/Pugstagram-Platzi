<script>
  let {nickname, name} = $props();
</script>

<style>
  .Profile-content {
    display: flex;
    align-items: center;
  }
  .Profile-avatar img {
    width: 42px;
    height: 42px;
    border-radius: 50%;
  }
  .Profile-info {
    margin: 0 0 0 0.5em;
  }
  .Profile-info h2 {
    font-size: 14px;
    color: black;
    margin: 0;
    padding: 0;
  }
  .Profile-info span {
    font-size: 12px;
    font-weight: normal;
  }
</style>



<div class="Profile">
    <div class="Profile-content">
        <div class="Profile-avatar">
            <img src="https://lh3.googleusercontent.com/a/ACg8ocJgjpXbPxs6C17GaljclZhqJnc6R55uZd3ov_mYqjACleJ5Tc0=s200-c" alt="">
        </div>
        <dic class="Profile-info">
            <h2>{nickname}</h2>
            <span>{name}</span>
        </dic>
    </div>
</div>