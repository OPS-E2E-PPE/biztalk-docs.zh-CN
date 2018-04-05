---
title: UpdateEx 方法 |Microsoft 文档
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
ms.openlocfilehash: 7a6a64c6709eb9806612518c551372ba45d1a454
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="updateex-method"></a>UpdateEx 方法
用于更新属性基于输入的密钥参数 (key1、 key2，... keyn)。 使用 `UpdateEx` 时，不能删除集合中的项目。 可使用单独方法进行删除。 有关详细信息，请参阅[DeleteOnly 方法](../core/deleteonly-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
UpdateEx (key1, key2, ... keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a>Parameters  
  
|参数|Description|  
|---------------|-----------------|  
|`key`|服务器数据库中必须存在的一组参数，或发生的错误。 这些键对应于为特定组件接口定义的一组 Get 键。|  
|`correctionMode`|布尔型标志。 设置为 true 时，可通过更新字段值或将新项插入集合来修改生效日期项的组件接口。 特别是，允许在当前生效日期之前修改具有 EFFDT 的项目。 如果此标志未设置为 TRUE，则对这些项目的任何修改将导致从 PeopleSoft 服务器返回错误。<br /><br /> 仅对包含生效日期项的组件接口公开 `correctionMode` 参数。 否则，不会作为参数的一部分显示。<br /><br /> 您应避免在生产环境中将 `correctionMode` 设置为 TRUE。 （这是也 PeopleSoft 的建议。）不应修改过去的 EFFDT 键确定已发生的事件。 允许创建审核记录。 `UpdateEx` 中的 `correctionMode` 标志允许跳过此安全机制。 建议的做法是通过设置项目中的字段并添加（而不是删除）更新项目来停用过去的事件。|  
|`interactiveMode`|用于错误处理的标志。<br /><br /> 访问组件接口中的属性时，PeopleSoft Enterprise 的 BizTalk 适配器使用 PeopleSoft 提供的用于读写组件接口中各个字段的 API；但是，这些更改并不是逐一传播到 PeopleSoft 服务器的。 psjoa.jar（与 PeopleSoft Enterprise 的 BizTalk 适配器交互）会将所有更改打包，然后将这些更改通过一个程序包发送到服务器。 如果各个更新中有任何一个失败，则会返回一般错误，但未指明确切问题。 将交互模式设置为 TRUE 时，每个字段更新都会单独发送到服务器。 这样会对性能产生实质影响，但是在更新失败的情况下（例如，如果使用无效的值设置字段）会提供特定错误信息。<br /><br /> `interactiveMode` 可提供最佳性能，并提供字段更新级别的错误报告。 要正确使用此功能，建议您将 `interactiveMode` 设置为 FALSE 来进行常规调用。 这应该不会对性能带来影响。 如果返回错误，则可以将 `interactiveMode` 标志设置为 TRUE 来重试同一调用。 调用失败时，服务器将返回更准确的错误消息。|  
  
### <a name="remarks"></a>注释  
 调用此函数时，将使用输入参数属性替换与这些键相对应的记录的属性。 将删除原始记录的所有集合，并替换为输入参数中的集合。 这些集合的大小无需匹配，因为 `UpdateEx` 中的过程将删除所有现有集合项目，然后插入指定项目。  
  
 如果组件接口的属性包含生效日期项目，则属性参数必须包含所有未来的生效日期项目，因为原始列表已被替换。 这提供了添加和删除未来的生效日期项目的机制；但是，如果属性还包含过去的生效日期项目，则会因为无法修改过去的生效日期项目而返回错误。 如果还包含当前的生效日期项目，则将忽略该项目。 这允许客户端调用`Get()`与`getHistoryItems`参数设置为 False，和修改任何将来的有效日期项或添加新将来生效日期的项目，以及将作为参数传递结构中`UpdateEx()`函数。  
  
 如果组件接口没有任何键，这种情况下只存在一个实例，则 `UpdateEx()` 方法的格式如下：  
  
```  
UpdateEx(correctionMode, interactiveMode, properties)  
```  
  
> [!NOTE]
>  如果启用了组件接口中的 PeopleSoft `UpdateEx()` 和 `Get` 函数，则将提供 PeopleSoft Enterprise 的 BizTalk 适配器的 `Save` 方法。  
  
## <a name="see-also"></a>另请参阅  
 [附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)