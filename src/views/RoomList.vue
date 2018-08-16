<template>
  <div id="roomList">
    <div class="option">
      <Button size="large" icon="md-add" type="primary">新建房间</Button>
      <Button size="large" icon="md-search" type="info">搜索房间</Button>
    </div>
    <div class="list">
      <Card v-for="room in roomList" :key="room.id" class="card">
        <p slot="title" class="room-name"><Icon type="md-home"/><span class="room-name">{{room.name}}</span><Icon type="md-lock" v-show="room.locked"/></p>
        <Button size="small" slot="extra" shape="circle" icon="ios-send" type="success" class="btn-enter" :disabled="!(room.max>room.users)">{{room.max>room.users?'进入':'已满'}}</Button>
        <div class="card-body">
          <span>房主:</span>
          <img src="../assets/touxiang.jpg" alt="">
          <span>{{room.master}}</span>
          <Badge :text="room.users + '/' + room.max" :type="room.max>room.users?'primary':'error'" class="users-num"></Badge>
        </div>
      </Card>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RoomList',
  data () {
    return {
      newRoom: {
        name: '',
        password: ''
      },
      roomList: [
        {
          id: 1,
          name: 'fxo的一号房间',
          master: 'fxosleeping',
          max: 2,
          users: 2,
          imgUrl: '../assets/touxiang.jpg',
          locked: false
        },
        {
          id: 1,
          name: 'fxo的二号房间',
          master: 'fxosleeping',
          max: 2,
          users: 1,
          imgUrl: '../assets/touxiang.jpg',
          locked: true
        }
      ]
    }
  }
}
</script>
<style>
#roomList{
  margin-top: 10px;
  width: 100%;
}
.option{
  width: 100%;
}
.option button{
  margin-left: 1%;
  width: 48%;
}
.list{
  margin-bottom: 10px;
}
.ivu-icon-md-home{
  font-size: 16px;
  margin-right: 5px;
}
.card{
  margin-top: 15px;
}
.room-name{
  color: #515a6e;
  margin-right: 5px;
}
.card-body span{
  vertical-align: middle;
}
.card-body img{
  border-radius: 50%;
  vertical-align: middle;
  margin: 0 5px;
  width: 20px;
}
.users-num{
  float: right;
}
</style>
