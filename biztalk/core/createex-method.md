---
title: CreateEx 方法 |Microsoft 文档
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
ms.openlocfilehash: b163bfbe7811c37208297aa0a61bfe91cabacde4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238285"
---
# <a name="createex-method"></a>CreateEx 方法
使用一组唯一的项和指定的属性创建新记录。  
  
## <a name="syntax"></a>语法  
  
```  
CreateEx  
(key1, key2, ..., keyn, interactiveMode, properties)  
```  
  
## <a name="parameters"></a>Parameters  
  
|参数|Description|  
|---------------|-----------------|  
|`Key in/out parameter`|各个项参数（key1、key2...keyn），必须提供。<br /><br /> 此项集不得存在于服务器数据库中，即它们必须是唯一的。<br /><br /> 这些项对应于为特定组件接口定义的“CreateEx”项集。|  
|`interactiveMode`|错误处理。<br /><br /> 访问组件接口中的属性时，用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用 PeopleSoft 提供的 API，这些 API 可以读取和写入组件接口中的各个字段；但是，这些更改不会一次一个地传播到 PeopleSoft 服务器上。 相反，（与之 PeopleSoft 企业 BizTalk 适配器交互） psjoa.jar 包的所有更改，并将所做的更改发送到一个包中的服务器。<br /><br /> 如果各个更新中有任何一个失败，则会返回一般错误，但未指明确切问题。 将交互模式设置为 TRUE 时，每个字段更新都会单独发送到服务器。 这样会对性能产生实质影响，但是在更新失败的情况下（例如，如果使用无效的值设置字段）会提供特定错误信息。<br /><br /> interactiveMode 提供最佳性能，并在字段更新级别提供错误报告。 若要正确使用此功能，建议将 interactiveMode 设置为 FALSE 的情况下进行正常调用。 这应该不会对性能带来影响。 如果返回错误，相同的调用可以重试 interactiveMode 标志设置为 TRUE。 调用失败时，服务器将返回更准确的错误消息。|  
|`properties`|包含组件接口所有属性的结构。 当调用 `CreateEx` 方法时，这些属性会插入到使用特定项创建的记录中。|  
  
## <a name="remarks"></a>注释  
 在某些情况下，通常的做法是在不具有显示项集的情况下调用 `CreateEx()`，由 `CreateEx` 函数返回这些项。 在服务器上触发的 PeopleCode 支持此行为。 例如，若要创建采购订单，客户端可能不知道下一个可用的 PO 编号。 通过将 NEXT 指定为 PO 编号项，调用会触发 PeopleCode，这将确定下一个可用 PO 编号。 此信息必须返回到调用客户端（使用 in/out 项参数）。  
  
> [!NOTE]
>  此机制发挥作用，键还必须是 0 级的属性。 否则，返回原始的密钥。  
  
 如果启用组件接口中的 PeopleSoft 创建和保存功能，则会提供用于 PeopleSoft Enterprise 的 BizTalk 适配器 `CreateEx()` 方法。  
  
## <a name="see-also"></a>另请参阅  
 [附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)