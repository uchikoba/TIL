PHPでは関数をネストさせることが可能だった
```php
function foo() {
    echo "FOO\n";
    
    function bar() {
        echo "BAR\n";
    }
}
```

こういう書き方が可能。

かつ、関数bar()に関しては、関数foo()を実行した後であれば、関数foo()以外の場所のどこからでも呼び出すことが可能。
