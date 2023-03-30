# 如何建立一个无服务器、搜索引擎友好的 React 博客

> 原文：<https://thenewstack.io/build-serverless-seo-friendly-react-blog/>

```
<span class="pl-k">import</span>  <span class="pl-smi">React</span>,  {  <span class="pl-smi">Component</span>  }  <span class="pl-k">from</span>  <span class="pl-s"><span class="pl-pds">'</span>react<span class="pl-pds">'</span></span>;
<span class="pl-k">import</span>  {  <span class="pl-smi">Link</span>  }  <span class="pl-k">from</span>  <span class="pl-s"><span class="pl-pds">'</span>react-router<span class="pl-pds">'</span></span>
<span class="pl-k">import</span>  <span class="pl-smi">Butter</span>  <span class="pl-k">from</span>  <span class="pl-s"><span class="pl-pds">'</span>buttercms<span class="pl-pds">'</span></span>

<span class="pl-k">const</span>  <span class="pl-c1">butter</span>  <span class="pl-k">=</span>  <span class="pl-en">Butter</span>(<span class="pl-s"><span class="pl-pds">'</span>de55d3f93789d4c5c26fb07445b680e8bca843bd<span class="pl-pds">'</span></span>);

<span class="pl-k">class</span>  <span class="pl-en">BlogHome</span>  <span class="pl-k">extends</span>  <span class="pl-e">Component</span>  {

  <span class="pl-en">constructor</span>(<span class="pl-smi">props</span>)  {
    <span class="pl-c1">super</span>(props);

    <span class="pl-c1">this</span>.<span class="pl-smi">state</span>  <span class="pl-k">=</span>  {
      loaded<span class="pl-k">:</span>  <span class="pl-c1">false</span>
    };
  }

  <span class="pl-en">fetchPosts</span>(<span class="pl-smi">page</span>)  {
    <span class="pl-smi">butter</span>.<span class="pl-smi">post</span>.<span class="pl-en">list</span>({page<span class="pl-k">:</span>  page,  page_size<span class="pl-k">:</span>  <span class="pl-c1">10</span>}).<span class="pl-en">then</span>((<span class="pl-smi">resp</span>)  <span class="pl-k">=&gt;</span>  {
      <span class="pl-c1">this</span>.<span class="pl-en">setState</span>({
        loaded<span class="pl-k">:</span>  <span class="pl-c1">true</span>,
        resp<span class="pl-k">:</span>  <span class="pl-smi">resp</span>.<span class="pl-c1">data</span>
      })
    });
  }

  <span class="pl-en">componentWillMount</span>()  {
    <span class="pl-k">let</span>  page  <span class="pl-k">=</span>  <span class="pl-c1">this</span>.<span class="pl-smi">props</span>.<span class="pl-smi">params</span>.<span class="pl-smi">page</span>  <span class="pl-k">||</span>  <span class="pl-c1">1</span>;

    <span class="pl-c1">this</span>.<span class="pl-en">fetchPosts</span>(page)
  }

  <span class="pl-en">componentWillReceiveProps</span>(<span class="pl-smi">nextProps</span>)  {
    <span class="pl-c1">this</span>.<span class="pl-en">setState</span>({loaded<span class="pl-k">:</span>  <span class="pl-c1">false</span>});

    <span class="pl-k">let</span>  page  <span class="pl-k">=</span>  <span class="pl-smi">nextProps</span>.<span class="pl-smi">params</span>.<span class="pl-smi">page</span>  <span class="pl-k">||</span>  <span class="pl-c1">1</span>;

    <span class="pl-c1">this</span>.<span class="pl-en">fetchPosts</span>(page)
  }

  <span class="pl-en">render</span>()  {
    <span class="pl-k">if</span>  (<span class="pl-c1">this</span>.<span class="pl-smi">state</span>.<span class="pl-smi">loaded</span>)  {
      <span class="pl-k">const</span>  {  <span class="pl-c1">next_page</span>,  <span class="pl-c1">previous_page</span>  }  <span class="pl-k">=</span>  <span class="pl-c1">this</span>.<span class="pl-smi">state</span>.<span class="pl-smi">resp</span>.<span class="pl-smi">meta</span>;

      <span class="pl-k">return</span>  (
        <span class="pl-k">&lt;</span>div<span class="pl-k">&gt;</span>
          {<span class="pl-c1">this</span>.<span class="pl-smi">state</span>.<span class="pl-smi">resp</span>.<span class="pl-c1">data</span>.<span class="pl-en">map</span>((<span class="pl-smi">post</span>)  <span class="pl-k">=&gt;</span>  {
            <span class="pl-k">return</span>  (
              <span class="pl-k">&lt;</span>div key<span class="pl-k">=</span>{<span class="pl-smi">post</span>.<span class="pl-smi">slug</span>}<span class="pl-k">&gt;</span>
                <span class="pl-k">&lt;</span>Link to<span class="pl-k">=</span>{<span class="pl-s"><span class="pl-pds">`</span>/post/<span class="pl-s1"><span class="pl-pse">${</span><span class="pl-smi">post</span>.<span class="pl-smi">slug</span><span class="pl-pse">}</span></span><span class="pl-pds">`</span></span>}<span class="pl-k">&gt;</span>{<span class="pl-smi">post</span>.<span class="pl-c1">title</span>}<span class="pl-k">&lt;</span><span class="pl-k">/</span>Link<span class="pl-k">&gt;</span>
              <span class="pl-k">&lt;</span><span class="pl-k">/</span>div<span class="pl-k">&gt;</span>
            )
          })}

          <span class="pl-k">&lt;</span>br  <span class="pl-k">/</span><span class="pl-k">&gt;</span>

          <span class="pl-k">&lt;</span>div<span class="pl-k">&gt;</span>
            {previous_page  <span class="pl-k">&amp;&amp;</span>  <span class="pl-k">&lt;</span>Link to<span class="pl-k">=</span>{<span class="pl-s"><span class="pl-pds">`</span>/p/<span class="pl-s1"><span class="pl-pse">${</span>previous_page<span class="pl-pse">}</span></span><span class="pl-pds">`</span></span>}<span class="pl-k">&gt;</span>Prev<span class="pl-k">&lt;</span><span class="pl-k">/</span>Link<span class="pl-k">&gt;</span>}

            {next_page  <span class="pl-k">&amp;&amp;</span>  <span class="pl-k">&lt;</span>Link to<span class="pl-k">=</span>{<span class="pl-s"><span class="pl-pds">`</span>/p/<span class="pl-s1"><span class="pl-pse">${</span>next_page<span class="pl-pse">}</span></span><span class="pl-pds">`</span></span>}<span class="pl-k">&gt;</span>Next<span class="pl-k">&lt;</span><span class="pl-k">/</span>Link<span class="pl-k">&gt;</span>}
          <span class="pl-k">&lt;</span><span class="pl-k">/</span>div<span class="pl-k">&gt;</span>
        <span class="pl-k">&lt;</span><span class="pl-k">/</span>div<span class="pl-k">&gt;</span>
      );
    }  <span class="pl-k">else</span>  {
      <span class="pl-k">return</span>  (
        <span class="pl-k">&lt;</span>div<span class="pl-k">&gt;</span>
          Loading<span class="pl-k">...</span>
        <span class="pl-k">&lt;</span><span class="pl-k">/</span>div<span class="pl-k">&gt;</span>
      )
    }
  }
}

<span class="pl-k">export</span>  <span class="pl-c1">default</span>  <span class="pl-smi">BlogHome</span>;

```