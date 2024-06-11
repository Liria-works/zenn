この記事は、以前よりQiitaで

# テクスチャのカラースペース

シェーダーエディターにテクスチャを配置したとき、RoughnessやMetallicなどはカラースペースを**非カラー**にする必要があります。  

逆にsRGBのままでいいのはBaseColorやSubSurfaceColorなど限定的で、毎回たくさんのノードでカラースペースを変えなければならず面倒くさいので、デフォルトで非カラーにしてしまいます。

![](/images/001.png)


# config.ocioを編集

以下のファイルをエディタで開きます。
`{blender_install_directory}/{version}/datafiles/colormanagement/config.ocio`

    # Default color space for byte image
    default_byte: sRGB

という項目があります。`sRGB`を`Non-Color`に書き換えて保存します。

    # Default color space for byte image
    default_byte: Non-Color

Blenderを再起動しシェーダーエディターに画像をドラッグアンドドロップすると、デフォルトでカラースペースが非カラーになっています。

> [!NOTE]
> Blenderバージョンにより、config.ocioの場所が異なる可能性があります。
