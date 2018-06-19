---
title: Get 方法 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Get method
ms.assetid: 0e621077-f0ef-495c-ba6b-0c6154f48113
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d56b060cc261f707a4aa7b0d6a496a62707c4dca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246517"
---
# <a name="get-method"></a>Get 方法
用于检索属性基于输入的密钥参数 (key1、 key2，... keyn)。 输出参数是一个结构，该结构包含与关键字参数匹配的记录的属性。 如果组件接口具有只有一个实例 （即，没有任何键） 的 Get 函数中不包含任何关键参数。 另请参阅[Find 方法](../core/find-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
Get (key1, key2, ... keyn, properties)  
Get (key1, key2, ... keyn, getHistoryItems, properties)  
```  
  
## <a name="parameters"></a>Parameters  
  
|参数|Description|  
|---------------|-----------------|  
|`key`|一组必须存在于服务器数据库中; 的参数否则将出现错误。 按照对特殊组件接口进行的定义，这些关键字对应于 Get 关键字组。|  
|`properties`|包含组件接口属性的完整结构，在调用完成时会返回此结构。|  
|`getHistoryItems`|一个布尔值。 如果组件接口的属性包含级别 0 以下的有效日期项（即，名为 EFFDT 的关键字段），则还需要附加参数 `getHistoryItems`。<br /><br /> 如果值为：<br /><br /> -True-所有有效的发布日期为项返回为一系列 （它无法在任何级别中嵌入）。 其中包括所有过去的有效日期项、当前的有效日期项以及所有将来的有效日期项<br />-False-返回仅当前和将来的所有有效过时的项目。 如果在同一个实例上更新的后续调用将进行，然后`getHistoryItems`应设置为 False。|  
  
### <a name="remarks"></a>注释  
 如果组件接口的属性包含级别 0 以下的有效日期项（即，名为 EFFDT 的关键字段），则还需要一个附加参数 `getHistoryItems`。 此参数为布尔型。 如果将其设置为 True，则所有有效日期项将作为一个序列（可嵌入到任意级别）返回。 其中包括所有过去的有效日期项、当前的有效日期项以及所有将来的有效日期项。 如果将 `getHistoryItems` 参数设置为 False，则只会返回当前和所有将来的有效日期项。 如果将来还会对同一实例调用更新，则应将 `getHistoryItems` 设置为 False。 另请参阅[UpdateEx 方法](../core/updateex-method.md)。  
  
 如果组件接口没有关键字（即，仅存在一个实例），则 `Get()` 方法的形式如下：  
  
```  
Get(properties)  
```  
  
 有关有效日期项的详细信息，请参阅 PeopleSoft Enterprise 文档。  
  
> [!NOTE]
>  PeopleSoft 企业 BizTalk 适配器`Get()`提供方法是，如果 PeopleSoft`Get`启用组件界面中的函数。  
  
## <a name="see-also"></a>另请参阅  
 [附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)