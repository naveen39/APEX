## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/naveen39/APEX/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

<div class="post hentry uncustomized-post-template" itemprop="blogPost" itemscope="itemscope" itemtype="http://schema.org/BlogPosting">
<meta content="4574613534265035266" itemprop="blogId">
<meta content="8709598656463183361" itemprop="postId">
<a name="8709598656463183361"></a>
<h3 class="post-title entry-title" itemprop="name">
<a href="https://bayyabuzz.blogspot.com/2021/04/object-schema-get-object-from-record-id.html">ReUsable Schema Snippets</a>
</h3>
<div class="post-header">
<div class="post-header-line-1"></div>
</div>
<div class="post-body entry-content" id="post-body-8709598656463183361" itemprop="description articleBody">



  

    <table style="background-color: #0000001f; border: 1px solid #dddddd;">
      <tbody><tr>
        <td>
          <p><br></p><h4 style="text-align: left;"><span>&nbsp;&nbsp; &nbsp;</span><span>&nbsp;&nbsp; &nbsp;</span><b><span>&nbsp; Get Object from Record Id:</span></b></h4>
          <blockquote style="border: none; margin: 0 0 0 40px; padding: 0px;"><p style="text-align: left;">Id&nbsp; <span style="background-color: #fcff01;">recordId </span>= '100xxxxxxxxxxxxabc';</p></blockquote><blockquote style="border: none; margin: 0 0 0 40px; padding: 0px;"><p style="text-align: left;">Schema.DescribeSObjectResult objectDescribe = <span style="background-color: #fcff01;">recordId</span>.getSobjectType().getDescribe();</p></blockquote><blockquote style="border: none; margin: 0 0 0 40px; padding: 0px;"><p style="text-align: left;">String objectName = objectDescribe.getName();</p></blockquote>
        </td>
      </tr>

    </tbody></table><br>

    <h2>Get Record Type Id Dynamically </h2>

    <table style="background-color: #0000001f; border: 1px solid #dddddd;">
      <tbody><tr>
        <td>
          <p><br></p><h4 style="text-align: left;"><span>&nbsp;&nbsp; &nbsp;</span><span>&nbsp;&nbsp; &nbsp;</span><b><span>&nbsp; Get Record Type Id by&nbsp;</span>&nbsp;Record Type Label:</b></h4><blockquote style="border: none; margin: 0px 0px 0px 40px; padding: 0px; text-align: left;"><p>String <span style="background-color: #fcff01;">recordTypeLabel</span>='Parent Account';</p><p>String <span style="background-color: #fcff01;">ObjectAPI</span>='Account';</p></blockquote><blockquote style="border: none; margin: 0px 0px 0px 40px; padding: 0px; text-align: left;"><div style="text-align: left;">String accRecordTypeID =</div></blockquote><blockquote style="border: none; margin: 0 0 0 40px; padding: 0px;"><blockquote style="border: none; margin: 0px 0px 0px 40px; padding: 0px; text-align: left;"><div style="text-align: left;">Schema.getGlobalDescribe().get(<span style="background-color: #fcff01;">ObjectAPI</span>).getDescribe().getRecordTypeInfosByName().</div></blockquote></blockquote><blockquote style="border: none; margin: 0 0 0 40px; padding: 0px;"><blockquote style="border: none; margin: 0 0 0 40px; padding: 0px;"><blockquote style="border: none; margin: 0px 0px 0px 40px; padding: 0px; text-align: left;"><div style="text-align: left;">get(<span style="background-color: #fcff01;">recordTypeLabel</span>).getRecordTypeId();</div></blockquote></blockquote></blockquote>          </td>
      </tr>
    </tbody></table><br>

    <table style="background-color: #0000001f; border: 1px solid #dddddd;">
      <tbody><tr>
        <td>
          <p><br></p><h4>&nbsp;&nbsp;&nbsp; &nbsp;<b>&nbsp; Get Record Type Id by&nbsp;&nbsp;Record Type Developer Name:</b></h4><blockquote style="border: none; margin: 0px 0px 0px 40px; padding: 0px;"><p>String&nbsp;<span style="background-color: #fcff01;">recordTypeDeveloperName</span>='Parent_Account';</p><p>String&nbsp;<span style="background-color: #fcff01;">ObjectAPI</span>='Account';</p></blockquote><blockquote style="border: none; margin: 0px 0px 0px 40px; padding: 0px;">String accRecordTypeID =</blockquote><blockquote style="border: none; margin: 0px 0px 0px 40px; padding: 0px;"><blockquote style="border: none; margin: 0px 0px 0px 40px; padding: 0px;">Schema.getGlobalDescribe().get(<span style="background-color: #fcff01;">ObjectAPI</span>).getDescribe().getRecordTypeInfosByDeveloperName().get(<span style="background-color: #fcff01;">recordType</span><span style="background-color: #fcff01;">DeveloperName</span>).getRecordTypeId();</blockquote></blockquote><p>&nbsp;</p>
        </td>
      </tr>

    </tbody></table><br>

    <h2>Get Field Type Dynamically </h2>

    <table style="background-color: #0000001f; border: 1px solid #dddddd;">
      <tbody><tr>
        <td>
          <p>&nbsp;</p><blockquote style="border: none; margin: 0 0 0 40px; padding: 0px;"><p style="text-align: left;"><b>GET Field Type Dynamically</b>&nbsp;</p></blockquote><blockquote style="border: none; margin: 0px 0px 0px 40px; padding: 0px; text-align: left;"><div>String <span style="background-color: #fcff01;">objectAPIName</span> = 'Account';</div><div>String <span style="background-color: #fcff01;">fieldAPIName</span> = 'Name';</div><div><br></div><div>SObjectType r = ( (SObject) Type.forName('Schema.'+<span style="background-color: #fcff01;">objectAPIName</span>).newInstance())).</div></blockquote><blockquote style="border: none; margin: 0 0 0 40px; padding: 0px;"><blockquote style="border: none; margin: 0 0 0 40px; padding: 0px;"><blockquote style="border: none; margin: 0 0 0 40px; padding: 0px;"><blockquote style="border: none; margin: 0px 0px 0px 40px; padding: 0px; text-align: left;"><div style="text-align: left;">getSObjectType();</div></blockquote></blockquote></blockquote></blockquote><blockquote style="border: none; margin: 0 0 0 40px; padding: 0px;"><p style="text-align: left;">&nbsp;DescribeSObjectResult d = r.getDescribe();</p></blockquote><blockquote style="border: none; margin: 0px 0px 0px 40px; padding: 0px; text-align: left;"><div>System.debug(d.fields.getMap().get(<span style="background-color: #fcff01;">fieldAPIName</span>).getDescribe().getType());</div></blockquote>
        </td>
      </tr>

    </tbody></table><br>

    <div style="text-align: left;"><i><a href="https://developer.salesforce.com/docs/atlas.en-us.apexref.meta/apexref/apex_class_Schema_RecordTypeInfo.htm" target="_blank"><b><u>Reference Link</u></b></a></i></div><p></p><p>&nbsp;</p><br>


<div style="clear: both;"></div>
</div>
<div class="post-footer">
<div class="post-footer-line post-footer-line-1">
<span class="post-author vcard">
</span>
<span class="post-timestamp">
</span>
<span class="post-comment-link">
</span>
<span class="post-icons">
<span class="item-control blog-admin pid-1972702472">
<a href="https://www.blogger.com/post-edit.g?blogID=4574613534265035266&amp;postID=8709598656463183361&amp;from=pencil" title="Edit Post">
<img alt="" class="icon-action" height="18" src="https://resources.blogblog.com/img/icon18_edit_allbkg.gif" width="18">
</a>
</span>
</span>
<div class="post-share-buttons goog-inline-block">
<a class="goog-inline-block share-button sb-email" href="https://www.blogger.com/share-post.g?blogID=4574613534265035266&amp;postID=8709598656463183361&amp;target=email" target="_blank" title="Email This"><span class="share-button-link-text">Email This</span></a><a class="goog-inline-block share-button sb-blog" href="https://www.blogger.com/share-post.g?blogID=4574613534265035266&amp;postID=8709598656463183361&amp;target=blog" onclick="window.open(this.href, &quot;_blank&quot;, &quot;height=270,width=475&quot;); return false;" target="_blank" title="BlogThis!"><span class="share-button-link-text">BlogThis!</span></a><a class="goog-inline-block share-button sb-twitter" href="https://www.blogger.com/share-post.g?blogID=4574613534265035266&amp;postID=8709598656463183361&amp;target=twitter" target="_blank" title="Share to Twitter"><span class="share-button-link-text">Share to Twitter</span></a><a class="goog-inline-block share-button sb-facebook" href="https://www.blogger.com/share-post.g?blogID=4574613534265035266&amp;postID=8709598656463183361&amp;target=facebook" onclick="window.open(this.href, &quot;_blank&quot;, &quot;height=430,width=640&quot;); return false;" target="_blank" title="Share to Facebook"><span class="share-button-link-text">Share to Facebook</span></a><a class="goog-inline-block share-button sb-pinterest" href="https://www.blogger.com/share-post.g?blogID=4574613534265035266&amp;postID=8709598656463183361&amp;target=pinterest" target="_blank" title="Share to Pinterest"><span class="share-button-link-text">Share to Pinterest</span></a>
</div>
</div>
<div class="post-footer-line post-footer-line-2">
<span class="post-labels">
</span>
</div>
<div class="post-footer-line post-footer-line-3">
<span class="post-location">
</span>
</div>
</div>
</div>
