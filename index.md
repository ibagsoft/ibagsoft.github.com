---
layout: default
---
<div> 

    <section class="ib-container" id="ib-container">
        {% for post in site.categories.courses %}
        <article>
            <header>
                <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
                <span>{{ post.keywords }}</span>
            </header>
            <a href="{{ post.url }}">
            <p>{{ post.description }}</p>
            </a>
        </article>
        {% endfor %}
    </section>
    <script type="text/javascript">
            $(function() {
                
                var $container  = $('#ib-container'),
                    $articles   = $container.children('article'),
                    timeout;
                
                $articles.on( 'mouseenter', function( event ) {
                        
                    var $article    = $(this);
                    clearTimeout( timeout );
                    timeout = setTimeout( function() {
                        
                        if( $article.hasClass('active') ) return false;
                        
                        $articles.not( $article.removeClass('blur').addClass('active') )
                                 .removeClass('active')
                                 .addClass('blur');
                        
                    }, 65 );
                    
                });
                
                $container.on( 'mouseleave', function( event ) {
                    
                    clearTimeout( timeout );
                    $articles.removeClass('active blur');
                    
                });
            
            });
        </script>
</div>