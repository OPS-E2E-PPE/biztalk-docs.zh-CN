---
title: UpdateEx 方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UpdateEx method
ms.assetid: 2fa9c9cc-fd01-4765-8c31-facac188a19d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ac317a9c91f13dce2dadf74b3027ebf4d33390f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398630"
---
# <a name="updateex-method"></a>UpdateEx 方法
用于更新属性基于输入键参数 (key1、 key2，... keyn)。 当使用`UpdateEx`，不能删除集合中的项。 一个单独的方法进行删除。 有关详细信息，请参阅[DeleteOnly 方法](../core/deleteonly-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
UpdateEx (key1, key2, ... keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a>Parameters  
  
|参数|Description|  
|---------------|-----------------|  
|`key`|将出现一组必须存在于服务器数据库或错误的参数。 为特定组件接口定义，这些项对应于 Get 关键字组。|  
|`correctionMode`|一个布尔型标志。 何时设置为 true，允许修改的组件接口的有效日期项，方法是更新的字段值，或将新项插入到集合。 具体而言，它允许在当前的生效日期之前具有 EFFDT 的项目的修改。 如果没有此标志设置为 TRUE，对这些项的任何修改会导致从 PeopleSoft 服务器返回错误。<br /><br /> `correctionMode`参数仅公开为这些组件接口，即包含有效日期项。 否则，它不会显示作为参数的一部分。<br /><br /> 应避免设置`correctionMode`到生产环境中，则返回 TRUE。 （这是也 PeopleSoft 的建议。）不应修改过去的 EFFDT 键确定已发生的事件。 这允许创建审核线索。 `correctionMode`标记中`UpdateEx`允许绕过此安全机制。 建议的做法是过去的事件将通过在项目中，设置一个字段并添加 （而不删除） 停用更新后的项目。|  
|`interactiveMode`|一个标志，用于错误处理。<br /><br /> 访问组件接口中的属性时，适用于 PeopleSoft Enterprise 的 BizTalk 适配器使用 PeopleSoft 提供的 Api 的读取和写入组件接口; 中的各个字段但是，这些更改将不会传播到 PeopleSoft 服务器一次。 相反，psjoa.jar （与用于 PeopleSoft Enterprise 的 BizTalk 适配器进行交互） 包的所有更改，并将所做的更改发送到一个包中的服务器。 如果任何单个更新失败，一般会返回错误，这不会不找出实际的错误。 将交互模式设置为 TRUE 时，每个字段更新为发送到服务器单独。 这对性能，有重大影响，但如果更新失败 （例如，如果无效的值用于设置的字段） 提供特定错误的信息。<br /><br /> `interactiveMode`提供最大性能，并提供错误报告字段更新级别。 若要正确使用此功能，建议进行常规调用`interactiveMode`设置为 FALSE。 在性能上应该有任何影响。 如果返回错误，则使用，可以重试同一调用`interactiveMode`标志设置为 TRUE。 当调用失败时，服务器将返回更精确的错误消息。|  
  
### <a name="remarks"></a>备注  
 当调用此函数时，密钥相对应的记录的属性替换为输入的参数属性。 与原始记录的所有集合中删除，并替换为输入参数中。 这些集合的大小不具有匹配，因为中的过程`UpdateEx`是删除所有现有集合项目，然后插入指定的项目。  
  
 如果组件接口的属性包含生效日期的项目，则属性参数必须包含所有将来的有效日期项，因为原始列表已被替换。 这提供了机制，用于添加和删除未来的生效日期项目;但是，如果属性还包含过去的生效日期项目，被返回错误因为过去的生效日期的项不能进行修改。 如果还包括当前有效日期项，则将忽略它。 这允许客户端调用`Get()`与`getHistoryItems`参数设置为 False，并修改任何未来生效日期项目或添加新未来生效日期项目，并将作为参数传递的结构中`UpdateEx()`函数。  
  
 如果组件接口没有键，其中可存在一个实例，如`UpdateEx()`方法采用以下格式：  
  
```  
UpdateEx(correctionMode, interactiveMode, properties)  
```  
  
> [!NOTE]
>  用于 PeopleSoft Enterprise 的 BizTalk 适配器`UpdateEx()`方法提供如果 PeopleSoft`Get`和`Save`启用组件接口中的函数。  
  
## <a name="see-also"></a>请参阅  
 [附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)