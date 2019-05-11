---
title: Get 方法 |Microsoft Docs
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
ms.openlocfilehash: 0fbf3b80fce70cac1ac95d21c143cdb64fae6305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345144"
---
# <a name="get-method"></a>Get 方法
用来检索属性基于输入键参数 (key1、 key2，... keyn)。 输出参数是记录的一个包含密钥的参数匹配的属性的结构。 如果组件接口只有一个实例 （即，没有任何键），Get 函数不包含任何关键字参数。 另请参阅[Find 方法](../core/find-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
Get (key1, key2, ... keyn, properties)  
Get (key1, key2, ... keyn, getHistoryItems, properties)  
```  
  
## <a name="parameters"></a>Parameters  
  
|参数|Description|  
|---------------|-----------------|  
|`key`|一组必须存在于服务器数据库中; 的参数否则就会出错。 这些项对应于 Get 关键字组，为特定组件接口定义。|  
|`properties`|包含组件接口属性，在调用完成时会返回此的完整结构。|  
|`getHistoryItems`|一个布尔值。 如果组件接口的属性包含有效日期项级别 0 以下 （即，一个名为 EFFDT 键字段）`getHistoryItems`其他参数是必需的。<br /><br /> 如果值为：<br /><br /> -True-所有有效日期的项返回为一个序列 （可嵌入到任意级别）。 其中包括所有过去的有效日期的项、 当前的有效日期的项，以及所有将来的有效日期的项<br />-False，将返回仅当前和所有将来的有效日期的项。 如果在同一实例上更新的后续调用将进行，然后`getHistoryItems`应设置为 False。|  
  
### <a name="remarks"></a>备注  
 如果组件接口的属性包含有效日期项级别 0 （即，键字段名称为 EFFDT），以下附加参数， `getHistoryItems`，是必需的。 此参数是布尔类型。 如果设置为 True，所有有效日期的项是作为一个序列 （可嵌入到任意级别） 返回。 其中包括所有过去的有效日期的项、 当前的有效日期的项，以及所有将来的有效日期的项。 如果`getHistoryItems`参数设置为 False，仅返回当前和所有将来的有效日期的项是。 如果在同一实例上更新的后续调用都将然后`getHistoryItems`应设置为 False。 另请参阅[UpdateEx 方法](../core/updateex-method.md)。  
  
 如果组件接口没有键，这其中只有一个实例可以存在，这种情况则`Get()`方法采用以下格式：  
  
```  
Get(properties)  
```  
  
 有关有效日期项的详细信息，请参阅 PeopleSoft Enterprise 文档。  
  
> [!NOTE]
>  用于 PeopleSoft Enterprise 的 BizTalk 适配器`Get()`方法提供如果 PeopleSoft`Get`启用组件接口中的函数。  
  
## <a name="see-also"></a>请参阅  
 [附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)