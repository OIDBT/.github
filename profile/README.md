# OIDBT

**一个以去中心化为目标的资源分发实验**

当前实现的内容：
1. 由于传统资源如动画字幕组的资源集中在 BT，使用 [oidbt_bt_entry_getter](https://github.com/OIDBT/oidbt_bt_entry_getter) 从 BT 站爬取信息
2. 关联从 [oidbt_bangumi_ani_getter](https://github.com/OIDBT/oidbt_bangumi_ani_getter) 爬取的动画条目信息
3. 使用 [oidbt_torrent](https://github.com/OIDBT/oidbt_torrent) 解析种子只保留磁链，在本地生成 磁链 -> 条目 的映射
4. 通过 [oidbt_ipfs_synchronizer](https://github.com/OIDBT/oidbt_ipfs_synchronizer) 将映射信息上传到 IPFS/IPNS
5. 用户可用通过 JS 插件 [oidbt-bangumi-app](https://github.com/OIDBT/oidbt-bangumi-app) 在条目页面直接访问 IPFS 中的映射

特点：
* IPFS 是去中心化网络，理论上只要有人 pin 数据的 CID （类似于 BT 的做种），就能保证其他用户访问数据
* 用户自行设置自己信任的 IPNS 源，不再依附中心化平台的信任
* 由于用户自行设置源，所以上传者也不依附中心和平台，但上传者需要自行与用户达成信任
* 综上，**不再需要中心化的数据分享平台（例如 BT 站），且用户可帮助数据分发者上传数据（类似 BT 的保种）**
* 数据分发者可以直接分发 IPFS 数据，而不是分发传统 BT 数据，理论上用户可以直接在浏览器访问资源（例如直接播放视频）

所有数据开源地址：
* <https://ipfs.io/ipns/k51qzi5uqu5dlgex0mml8heng2ymlw8ro6yf0tu664sb2lrv3539rslvud62px>
  （从公共网关访问）
* <http://k51qzi5uqu5dlgex0mml8heng2ymlw8ro6yf0tu664sb2lrv3539rslvud62px.ipns.localhost:8080/>
  （从本地节点访问）
