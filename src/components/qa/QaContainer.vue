<template>
  <section>
    <h2>
      <i class="qaIcon"></i>
      <span>商品QA</span>
    </h2>
    <!-- 全部的 -->
    <div id="questionsArea">
      <!-- 第一行 全28件 和 新顺序-->
      <div class="page">
        <!-- 全28件 1/10 -->
        <div></div>
        <!-- 新顺序 -->
        <div></div>
      </div>
      <!-- QA解答部分 -->
      <div></div>
      <!-- 下面全28件 -->
      <div></div>
      <!--  注意 -->
      <div id="ZVCQAPost">
        <div class="zv-cqa-posting-rule">
          <p class="zv-cqa-posting-rule-title">ご注意ください</p>
          <ul>
            <li>
              「ニトリ商品Q&amp;A」は、お客様のご質問とニトリの回答を、他のお客様に参考にしていただくためのサービスです。
            </li>
            <!--<li>回答を要するご質問やお急ぎの方は<a class="g-link-u" href="https://www.nitori-net.jp/ec/input-inquiry/" target="_blank">お問い合わせフォームへ</a>ご連絡ください。</li>-->
            <li>
              ニトリが不適切と判断した際、後日投稿を削除する場合がございます。詳細はご利用ガイドの<a
                class="g-link-u"
                href="https://www.nitori-net.jp/ec/userguide/nitorinet/#zv-cqa"
                target="_blank"
                >ニトリ商品Q&amp;Aについて</a
              >をご確認ください。
            </li>
          </ul>
        </div>

        <input
          type="textbox"
          id="ZVQuestionTextarea"
          class="zv-textbox"
          placeholder="不明な点を質問（例：この製品には耐久性がありますか？）"
        />
        <div
          id="ZVAskPostArea"
          data-customerqa-message-after-post-question="送信しました。回答があるまでしばらくお待ちください。"
        >
          <p class="zv-error-message" id="ZVLoginErrorQuestion">
            質問を投稿するにはログインが必要です。
          </p>
          <p class="zv-error-message" id="ZVEmptyErrorQuestion">
            質問を入力してください。
          </p>
          <p class="zv-error-message" id="ZVSpamErrorQuestion">
            しばらく時間をおいて投稿してください。
          </p>
          <button type="button" id="ZVPostQuestionButton" class="zv-btn">
            質問を投稿
          </button>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {};
</script>
<style></style>
