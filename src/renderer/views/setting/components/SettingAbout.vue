<template lang="pug">
dt#about {{$t('setting__about')}}
dd
  p.small
    | 本软件完全免费，代码已开源，开源地址：
    span.hover.underline(:tips="$t('setting__click_open')" @click="openUrl('https://github.com/lyswhut/lx-music-desktop#readme')") https://github.com/lyswhut/lx-music-desktop
  p.small
    | 最新版网盘下载地址（网盘内有Windows、MAC版）：
    span.hover.underline(:tips="$t('setting__click_open')" @click="openUrl('https://www.lanzoui.com/b0bf2cfa/')") 网盘地址
    | &nbsp;&nbsp;密码：
    span.hover(:tips="$t('setting__click_copy')" @click="clipboardWriteText('glqw')") glqw
  p.small
    | 软件的常见问题可转至：
    span.hover.underline(:tips="$t('setting__click_open')" @click="openUrl('https://github.com/lyswhut/lx-music-desktop/blob/master/FAQ.md')") 常见问题
  p.small
    strong 本软件没有客服
    | ，但我们整理了一些常见的使用问题，
    strong 仔细 仔细 仔细
    | 地阅读常见问题后，
  p.small
    | 仍有问题可加企鹅群&nbsp;
    span.hover(:tips="$t('setting__click_open')" @click="openUrl('https://jq.qq.com/?_wv=1027&k=51ECeq2')") 830125506
    | &nbsp;反馈
    strong (为免满人，无事勿加，入群先看群公告)
    | ，或到 GitHub 提交&nbsp;
    span.hover.underline(:tips="$t('setting__click_open')" @click="openUrl('https://github.com/lyswhut/lx-music-desktop/issues')") issue

  br
  p.small
    | 如果你喜欢并经常使用洛雪音乐，并想要第一时间尝鲜洛雪的新功能&nbsp;
    span(style="text-decoration: line-through;") （当小白鼠）
    | ，
  p
    | 可以加入测试企鹅群&nbsp;
    span.hover(:tips="$t('setting__click_open')" @click="openUrl('https://qm.qq.com/cgi-bin/qm/qr?k=zR6aYosQoKb07g4FGFZdO9n9zL1dhFpE&jump_from=webapi')") 768786588
    | &nbsp;，注意：测试版的功可能会不稳定，
    strong 打算潜水的勿加

  br
  p.small 由于软件开发的初衷仅是为了对新技术的学习与研究，因此软件直至停止维护都将会一直保持纯净。

  p.small
    | 你已签署本软件的&nbsp;
    base-btn(min @click="handleShowPact") 许可协议
    | ，协议的在线版本在&nbsp;
    strong.hover.underline(:tips="$t('setting__click_open')" @click="openUrl('https://github.com/lyswhut/lx-music-desktop#%E9%A1%B9%E7%9B%AE%E5%8D%8F%E8%AE%AE')") 这里
    | &nbsp;。
  br

  p
    small By：
    | 落雪无痕
</template>

<script>
// import { ref, onBeforeUnmount } from '@renderer/utils/vueTools'
import { isShowPact } from '@renderer/core/share'
import { openUrl, clipboardWriteText } from '@renderer/utils'
import { currentStting } from '../setting'

export default {
  name: 'SettingAbout',
  setup() {
    const handleShowPact = () => {
      isShowPact.value = true
    }
    return {
      currentStting,
      openUrl,
      clipboardWriteText,
      handleShowPact,
    }
  },
}
</script>
