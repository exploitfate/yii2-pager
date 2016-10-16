# yii2-pager

Yii2 smart pager

Another LinkPager for [Yii2 framework](http://www.yiiframework.com/) pagination.


[![Latest Stable Version](https://poser.pugx.org/exploitfate/yii2-pager/v/stable)](https://packagist.org/packages/exploitfate/yii2-pager) 
[![Total Downloads](https://poser.pugx.org/exploitfate/yii2-pager/downloads)](https://packagist.org/packages/exploitfate/yii2-pager) 
[![Latest Unstable Version](https://poser.pugx.org/exploitfate/yii2-pager/v/unstable)](https://packagist.org/packages/exploitfate/yii2-pager) 
[![License](https://poser.pugx.org/exploitfate/yii2-pager/license)](https://packagist.org/packages/exploitfate/yii2-pager)

## Install

Best way is install via composer
```
composer require "exploitfate/yii2-pager"
```

## Usage

### Page size limit override default (optionally)

Setup page size limit in (frontend|backend|app)/config/main.php

```php

// Override default parameters for \yii\data\Pagination
\Yii::$container->set(
    \yii\data\Pagination::className(),
    [
        'pageSizeLimit' => [1, 1000],
        'defaultPageSize' => 200,
    ]
);

```

### Replace default LinkPager

In single GridView or ListView

```php

echo \yii\grid\GridView::widget(
    [
        'dataProvider' => $dataProvider,
        'filterModel' => $searchModel,
        'pager' => [
            'class' => \exploitfate\yii2\LinkPager::className(),
        ],
        
        // other settings
        
        'columns' => [
            ['class' => 'yii\grid\SerialColumn'],
    
            // other collumns
        ],
    ]
);
```

Also you can replace default LinkPager globally. 
Setup LinkPager for (GridView|ListView) in (frontend|backend|app)/config/main.php

GridView
```php

// Override default parameters for \yii\grid\GridView
\Yii::$container->set(
    \yii\grid\GridView::className(),
    [
        'pager' => [
            'class' => \exploitfate\yii2\LinkPager::className(),
        ],
     ]
);

```
ListView
```php

// Override default parameters for \yii\grid\GridView
\Yii::$container->set(
    \yii\grid\GridView::className(),
     [
        'pager' => [
            'class' => \exploitfate\yii2\LinkPager::className(),
        ],
     ]
);

```

### Widget

```php

echo \exploitfate\yii2\LinkPager::widget(
    [
        'pagination' => $dataProvider->getPagination(),
    ]
);

```

## License

The MIT License (MIT). See [LICENSE](LICENSE) file.