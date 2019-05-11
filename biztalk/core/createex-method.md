---
title: CreateEx 方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CreateEx method
ms.assetid: b62bbe25-b24d-42a7-a44c-c83521a6f0a6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23163739b18febd5642a704a6910241928e85730
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390119"
---
# <a name="createex-method"></a>CreateEx 方法
创建新记录使用一组的唯一键和指定的属性。  
  
## <a name="syntax"></a>语法  
  
```  
CreateEx  
(key1, key2, ..., keyn, interactiveMode, properties)  
```  
  
## <a name="parameters"></a>Parameters  
  
|参数|Description|  
|---------------|-----------------|  
|`Key in/out parameter`|各个项参数 （key1、 key2，...keyn)，必须提供。<br /><br /> 服务器数据库中不存在此项集，必须也就是说，它们必须是唯一的。<br /><br /> 这些密钥与为特定组件接口定义的 CreateEx 键集相对应。|  
|`interactiveMode`|错误处理。<br /><br /> 访问组件接口中的属性时，适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用 PeopleSoft 提供的 Api，它读取和写入组件接口; 中的各个字段但是，这些更改将不会传播到 PeopleSoft 服务器一次。 相反，psjoa.jar （与用于 PeopleSoft Enterprise 的 BizTalk 适配器进行交互） 包的所有更改，并将所做的更改发送到一个包中的服务器。<br /><br /> 如果任何单个更新失败，一般会返回错误，这不会不找出实际的错误。 将交互模式设置为 TRUE 时，每个字段更新为发送到服务器单独。 这对性能，有重大影响，但如果更新失败 （例如，如果无效的值用于设置的字段） 提供特定错误的信息。<br /><br /> InteractiveMode 提供最佳性能，并提供错误报告字段更新级别。 若要正确使用此功能，建议使用 interactiveMode 设置为 FALSE 进行正常调用。 在性能上应该有任何影响。 如果返回错误，则相同的调用可以重试 interactiveMode 标志设置为 TRUE。 当调用失败时，服务器将返回更精确的错误消息。|  
|`properties`|包含的组件接口的所有属性的结构。 当`CreateEx`方法调用时，这些属性插入到使用特定项创建的记录。|  
  
## <a name="remarks"></a>备注  
 在某些情况下，它是常见做法调用`CreateEx()`而无需显示项集的但`CreateEx`函数返回的键。 在服务器上触发的 PeopleCode 支持此行为。 例如，若要创建采购订单，客户端可能不知道什么是下一个可用 PO 编号。 通过指定为 PO 编号项下一步，调用会触发 PeopleCode，这将确定下一个可用 PO 编号。 此信息必须返回到调用客户端，使用在/out 项参数。  
  
> [!NOTE]
>  若要运行此机制，该密钥还必须是在级别 0 的属性。 否则，返回原始密钥。  
  
 用于 PeopleSoft Enterprise 的 BizTalk 适配器`CreateEx()`如果启用了组件接口中的 PeopleSoft 创建和保存函数提供方法。  
  
## <a name="see-also"></a>请参阅  
 [附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)