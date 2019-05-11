---
title: 适配器框架配置架构修饰标记 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d5d7f6b-2273-45a6-ba9d-43201760cf22
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdce504133ecb1de4763ce72b314fe39cea8fef3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361483"
---
# <a name="adapter-framework-configuration-schema-decoration-tags"></a>适配器框架配置架构修饰标记
可以使用本主题中的配置架构文件中所述的标记来显示和组织适配器属性页上的数据。  
  
 下图显示了如何 FTP 接收位置属性页将实施某些这些标记。  
  
 ![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")  
\<描述\>， \<displayname\>，并\<类别\>FTP 适配器属性页中的标记  
  
## <a name="designer"></a>\<designer\>  
 BizTalk 适配器框架修饰出现之间\<baf: designer\>标记和\</baf:designer\>结束标记。 \<Baf: designer\>标记有助于区分适配器框架\<appinfo\>和其他适配器提供\<appinfo\>信息。  
  
## <a name="category"></a>\<category\>  
 \<类别\>修饰包含用于将分组在属性网格中的项的字符串。 修饰将具有同一类别字符串的所有条目都显示为类别的从属条目。  
  
 可以进行本地化\<类别\>条目。  
  
## <a name="description"></a>\<description\>  
 \<说明\>修饰包含用于为属性网格底部的条目提供说明性文本的字符串。  
  
 可以进行本地化\<说明\>条目。  
  
## <a name="displayname"></a>\<displayname\>  
 \<Displayname\>修饰包含用于显示项的名称的字符串。 这使您可以使用空格、 短语等，它们将不允许为时\<元素\>或\<属性\>名称。  
  
 可以进行本地化\<displayname\>条目。  
  
## <a name="readonly"></a>\<readonly\>  
 \<Fixed =""\>修饰控制是否可以编辑字段。 "固定"的属性值`true`（默认值） 会使字段变为只读的。  
  
 在实现外部编辑器时，实现外部**TypeConverter**类并重写**getstandardvaluesexclusive （itypedescriptorcontext)** 方法相反。 返回`true`使字段成为只读的但保留权访问自定义编辑器。  
  
## <a name="browsable"></a>\<browsable\>  
 \<可浏览 show =""\>修饰控制字段是否出现在属性网格中。 一个"显示"属性值为`True`（默认值），网格中显示的字段。  
  
## <a name="converter"></a>\<converter\>  
 \<转换器程序集 =""\>修饰指定所需**TypeConverter**类名\<元素\>或者\<特性\>。 可选的"assembly"属性值指定包含所需的程序集的路径**TypeConverter**。 没有指定"assembly"值，类名必须包括全局程序集缓存的程序集名称、 密钥、 区域性和版本值。  
  
## <a name="editor"></a>\<editor\>  
 \<编辑器程序集 =""\>修饰指定所需**UITypeEditor**类名\<元素\>或者\<特性\>。 可选的"assembly"属性值指定包含所需的程序集的路径**UITypeEditor**。 没有指定"assembly"值，类名必须包括全局程序集缓存的程序集名称、 密钥、 区域性和版本值。  
  
## <a name="null-values-for-optional-enumerations"></a>可选枚举的 null 值  
 在使用可选的枚举，其中一个值应为\<none\>来表示 null 值。 这不是内置标记，但可能会通过提供一个枚举值，如果从 xsd: string 派生枚举作为无处理。 这是不可能从 xsd: int，派生的枚举，因为整数必须包含一个值。  
  
## <a name="see-also"></a>请参阅  
 [适配器框架配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)