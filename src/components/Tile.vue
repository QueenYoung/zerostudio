<template>
  <div class="tile is-ancestor">
  <div class="tile is-vertical is-8">
    <div class="tile">
      <div class="tile is-parent is-vertical">
        <article class="tile is-child box">
          <h3 class="title">
            工作室特色
          </h3>
          <p>
            算法底蕴扎实, 不限制学习的方向. C++ 大神帮你们打好大一基础
          </p>
        </article>
        <article class="tile is-child box">
          <h3 class="title">技术链</h3>
          <div class="field is-grouped is-grouped-multiline">
          <div class="control">
            <div class="tags has-addons">
              <span class="tag is-dark">前端</span>
              <span class="tag is-link">Good JS</span>
            </div>
          </div>

          <div class="control">
            <div class="tags has-addons">
              <span class="tag is-dark">前端</span>
              <span class="tag is-success">Beautiful Design</span>
            </div>
          </div>

          <div class="control">
            <div class="tags has-addons">
              <span class="tag is-dark">前端</span>
              <span class="tag is-primary">美女学姐帅哥学长</span>
            </div>
          </div>
        </div>

        <div class="field is-grouped is-grouped-multiline">
          <div class="control">
            <div class="tags has-addons">
              <span class="tag is-light">后端</span>
              <span class="tag is-success">Java</span>
            </div>
          </div>
          <div class="control">
            <div class="tags has-addons">
              <span class="tag is-light">后端</span>
              <span class="tag is-link">Python</span>
            </div>
          </div>
          <div class="control">
            <div class="tags has-addons">
              <span class="tag is-light">后端</span>
              <span class="tag is-primary">C/C++</span>
            </div>
          </div>
        </div>

        <div class="tags has-addons">
          <span class="tag is-danger">游戏</span>
          <span class="tag">Unity3D</span>
        </div>
        </article>
      </div>
      <div class="tile is-parent">
        <article class="tile is-child box">
          <h3 class="title">工作室背景</h3>
          <div class="content">
          <p>工作室成立于 2013 年, 是一个年轻个性化的团队. 我们在钟表老师的带领下,已经成为了一个很有影响力的工作室.</p>
          <p>在国家级比赛<strong>蓝桥杯</strong>中, 也取得了无可取代的成绩.各有学长获得过全国一二三等奖, 以及数十个省级奖项. 而这些学长学姐要么正在职场中快乐的工作着, 要么正在等待着你们的加入😉</p> 
          </div>
        </article>
      </div>
    </div>
    <div class="tile is-parent">
      <article class="tile is-child box">
      <nav class="level is-mobile">
        <div class="level-item has-text-centered">
          <div>
            <p class="heading">现任成员</p>
            <p class="title">13</p>
          </div>
        </div>
        <div class="level-item has-text-centered">
          <div>
            <p class="heading">大三</p>
            <p class="title">5</p>
          </div>
        </div>
        <div class="level-item has-text-centered">
          <div>
            <p class="heading">大二</p>
            <p class="title">8</p>
          </div>
        </div>
        <div class="level-item has-text-centered">
          <div>
            <p class="heading">大一</p>
            <p class="title">???</p>
          </div>
        </div>
      </nav>
      </article>
    </div>
  </div>
  <div class="tile is-parent">
    <article class="tile is-child box">
      <h3 class="title">工作室理念</h3>
      <div class="content">
       <p>零点工作室有一个很大的特点是对算法兴趣较浓. </p>
          <p>算法并不是想象中的那么高上大的东西, 我们培养的只是一种在解决问题过程中, 不断挑战自己突破自己, 最后优雅解决某个问题的能力. </p>
          <p>这不仅会提高你的<strong>编程自信</strong>, 也对之后的求职有极大的帮助.</p>
          <p>另外我们崇尚自由, 并不要求你一定要某个特定的语言. 无论网页设计, 还是游戏乃至服务器, 都有学长学姐.</p> 
      </div>
      </article>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'tiles'
  }
</script>