<template lang="html">

  <div>
    <section class="markdown">
      <h1>Iconfont</h1>
      <p>
        语义化的矢量图形。
      </p>
      <h2>图标的命名规范</h2>
      <p>
        我们为每个图标赋予了语义化的命名，命名规则如下:
      </p>
      <ul>
        <li>
          实心和描线图标保持同名，用 -o 来区分，比如 question-circle(实心) 和 question-circle-o(描线)；
        </li>
        <li>
          命名顺序：[icon名]-[形状可选]-[描线与否]-[方向可选]。
        </li>
      </ul>

      <h2>如何使用</h2>
      <p>使用 <v-icon></v-icon>标签声明组件，指定图标对应的 type 属性，示例代码如下:</p>
      <pre><code class="lang-html">&lt;v-icon type="link"&gt;&lt;/v-icon&gt;</code></pre>

      <p>最终会渲染为：</p>

      <pre><code class="lang-html">&lt;i class="anticon anticon-link"&gt;&lt;/i&gt;</code></pre>
      <h2>本地部署</h2>
      <p>图标组件使用 <a href="http://www.iconfont.cn/" target="blank">iconfont.cn</a>，默认公网可访问。如需本地部署，可参考 <a href="https://github.com/ant-design/antd-init/tree/master/examples/local-iconfont" target="blank">示例</a>。</p>
      <p style="color:#ff7800">* 点击下面的图标即可复制标签</p>
      
      <api-table
        :content='content'
      >
        <h3>Icon</h3>
      </api-table>

      <h2>图标列表</h2>
      <h3>方向性图标</h3>

      <ul class="anticons-list">
        <li class="icon-item" v-for="icon in icons1Obj" :class="{copied: Copied}" :data-clipboard-text="_getCopyCode(icon.name)">
          <span class="anticon anticon-{{icon.name}}"></span>
          <span class="anticon-class">{{icon.name}}</span>
        </li>
      </ul>

      <h3>提示建议性图标</h3>

      <ul class="anticons-list">
        <li class="icon-item" v-for="icon in icons2Obj" :class="{copied: Copied}" :data-clipboard-text="_getCopyCode(icon.name)">
          <span class="anticon anticon-{{icon.name}}"></span>
          <span class="anticon-class">{{icon.name}}</span>
        </li>
      </ul>

      <h3>网站通用图标</h3>

      <ul class="anticons-list">
        <li class="icon-item" v-for="icon in icons3Obj" :class="{copied: Copied}" :data-clipboard-text="_getCopyCode(icon.name)">
          <span class="anticon anticon-{{icon.name}}"></span>
          <span class="anticon-class">{{icon.name}}</span>
        </li>
      </ul>

    </section>
  </div>

</template>
<script>
  import apiTable from '../components/apiTable'
  import Clipboard from 'clipboard'

  export default {
    data: function () {
      return {
        icons1: ['step-backward', 'step-forward', 'fast-backward', 'fast-forward', 'shrink', 'arrow-salt', 'down', 'up', 'left', 'right', 'caret-down', 'caret-up', 'caret-left', 'caret-right', 'up-circle', 'down-circle', 'left-circle', 'right-circle', 'up-circle-o', 'down-circle-o', 'left-circle-o', 'right-circle-o', 'double-right', 'double-left', 'verticle-right', 'verticle-left', 'forward', 'backward', 'rollback', 'enter', 'retweet', 'swap', 'swap-left', 'swap-right', 'arrow-right', 'arrow-up', 'arrow-down', 'arrow-left', 'play-circle', 'play-circle-o', 'up-square', 'down-square', 'left-square', 'right-square', 'up-square-o', 'down-square-o', 'left-square-o', 'right-square-o'],
        icons2: ['question', 'question-circle-o', 'question-circle', 'plus', 'plus-circle-o', 'plus-circle', 'pause', 'pause-circle-o', 'pause-circle', 'minus', 'minus-circle-o', 'minus-circle', 'plus-square', 'plus-square-o', 'minus-square', 'minus-square-o', 'info', 'info-circle-o', 'info-circle', 'exclamation', 'exclamation-circle-o', 'exclamation-circle', 'close', 'close-circle', 'close-circle-o', 'close-square', 'close-square-o', 'check', 'check-circle', 'check-circle-o', 'check-square', 'check-square-o', 'clock-circle-o', 'clock-circle'],
        icons3: ['lock', 'unlock', 'android', 'apple', 'apple-o', 'area-chart', 'pie-chart', 'bar-chart', 'dot-chart', 'bars', 'book', 'calendar', 'cloud', 'cloud-download', 'code', 'code-o', 'copy', 'credit-card', 'delete', 'desktop', 'download', 'edit', 'ellipsis', 'file', 'file-text', 'file-unknown', 'file-pdf', 'file-excel', 'file-jpg', 'file-ppt', 'folder', 'folder-open', 'github', 'hdd', 'frown', 'frown-o', 'meh', 'meh-o', 'smile', 'smile-o', 'inbox', 'laptop', 'appstore-o', 'appstore', 'line-chart', 'link', 'logout', 'mail', 'menu-fold', 'menu-unfold', 'mobile', 'notification', 'paper-clip', 'picture', 'poweroff', 'reload', 'search', 'setting', 'share-alt', 'shopping-cart', 'tablet', 'tag','tag-o', 'tags', 'tags-o', 'to-top', 'upload', 'user', 'video-camera', 'windows','windows-o', 'ie', 'chrome', 'home', 'loading', 'cloud-upload-o', 'cloud-download-o', 'cloud-upload', 'cloud-o', 'star-o', 'star', 'heart-o', 'heart', 'environment', 'environment-o', 'eye', 'eye-o', 'camera', 'camera-o', 'aliwangwang', 'aliwangwang-o', 'save', 'team', 'solution', 'phone', 'filter', 'exception', 'export', 'customer-service', 'qrcode', 'scan', 'like', 'like-o', 'dislike', 'dislike-o', 'message', 'pay-circle', 'pay-circle-o', 'calculator', 'pushpin', 'pushpin-o', 'bulb', 'select'],
        Copied:false,
        type:String,
        content: [
          [
            'type',
            '图标类型',
            'String',
            '-'
          ],
          [
            'spin',
            '是否有旋转动画',
            'Boolean',
            'false'
          ]
        ]
      }
    },

    components: {
      apiTable
    },

    computed: {
      icons1Obj () {
        return this.icons1.map(name => {
            return {name, justCopied: false}
          })
      },
      icons2Obj () {
        return this.icons2.map(name => {
            return {name, justCopied: false}
          })
      },

      icons3Obj () {
        return this.icons3.map(name => {
            return {name, justCopied: false}
          })
      }
    },

    ready () {

      const clipboard = new Clipboard('.anticons-list li')
      var that = this
      clipboard.on('success', (e) => {
        var target= e.trigger

        target.className='icon-item copied'

        setTimeout(() => {
          target.className='icon-item'
        }, 1000)

    })
    },

    methods: {
      _getCopyCode: function(type) {
        return '<v-icon type="'+type+'"></v-icon>'
      },
      clickfunc: function(event){
        console.log(this);
        console.log(event);

      }
    }

  }

</script>
<style lang="less" scoped>

  .markdown > ul li {
    list-style: circle;
    margin-left: 20px;
  }

  .markdown pre {
    background: #F7F7F7;
    border-radius: 6px;
  }

  .markdown pre {
    margin: 1.2em 0;
    padding: 1em;
  }

  .markdown code {
    margin: 0 3px;
  }

  ul.anticons-list {
    margin: 20px 0;
    list-style: none;
    overflow: hidden;
  }
  ul.anticons-list li {
    float: left;
    margin: 5px 5px 5px 0;
    width: 155px;
    text-align: center;
    list-style: none;
    cursor: pointer;
    height: 110px; color: #5C6B77;
    -webkit-transition: all 0.2s ease;
    transition: all 0.2s ease;
    position: relative; padding-top: 10px;
  }
  ul.anticons-list li:hover {
    background-color: #4BB8FF;
    color: #fff;
    border-radius: 4px;
  }
  ul.anticons-list li.copied:hover {
    color: rgba(255,255,255,0.2);
  }
  ul.anticons-list li:after {
    position: absolute;
    top: 10px;
    left: 0;
    height: 100%;
    width: 100%;
    content: "Copied!";
    text-align: center;
    line-height: 110px;
    color: #fff;
    -webkit-transition: all 0.3s cubic-bezier(0.18, 0.89, 0.32, 1.28);
    transition: all 0.3s cubic-bezier(0.18, 0.89, 0.32, 1.28);
    opacity: 0;
  }
  ul.anticons-list li.copied:after {
    opacity: 1;
    top: 0;
  }
  .anticon {
    font-size: 26px;
    margin: 12px 0 16px;
  }
  .anticon-class {
    display: block;
    text-align: center;
    word-wrap: break-word;
  }

</style>


