---
title: DeleteOnly 方法 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DeleteOnly method
ms.assetid: 99e1d7af-1450-439b-882f-de677e593bee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3982c67b4c2eb572a57a4ad602b1d302f9b53ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deleteonly-method"></a>DeleteOnly 方法
可以删除集合中的项。  
  
## <a name="syntax"></a>语法  
  
```  
DeleteOnly(key1, key2, ..., keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a>Parameters  
  
|参数|Description|  
|---------------|-----------------|  
|`key`|是一套必须提供的参数。 此组的密钥必须存在于服务器数据库，或发生错误。 这些键对应于为特定组件接口定义的一组 Get 键。|  
|`correctionMode`|布尔型标志。 何时设置为 true，将集合中允许的过去生效日期的项目的删除。 具体而言，它允许在当前的生效日期之前具有 EFFDT 的项删除。 如果此标志未设置为 TRUE，则对这些项目的任何修改将导致从 PeopleSoft 服务器返回错误。 **注意：** `correctionMode`有关包含有效日期项这些组件接口仅公开自变量。 否则它将不显示作为自变量的一部分。|  
|`interactiveMode`|用于处理错误。<br /><br /> PeopleSoft 企业 BizTalk 适配器时访问组件接口中的属性，使用 PeopleSoft 提供 Api，它读取和写入单个字段中的组件接口;但是，这些更改将不会传播到 PeopleSoft server 一个一次。 相反，（与之 PeopleSoft 企业 BizTalk 适配器交互） psjoa.jar 包的所有更改，并将所做的更改发送到一个包中的服务器。 如果各个更新中有任何一个失败，则会返回一般错误，但未指明确切问题。 将交互模式设置为 TRUE 时，每个字段更新都会单独发送到服务器。 这样会对性能产生实质影响，但是在更新失败的情况下（例如，如果使用无效的值设置字段）会提供特定错误信息。<br /><br /> `interactiveMode` 参数提供了最大的性能，并且可以提供字段更新级别的错误报告。 要正确使用此功能，建议您将 `interactiveMode` 设置为 FALSE 来进行常规调用。 这应该不会对性能带来影响。 如果返回错误，相同的调用可以重试 interactiveMode 标志设置为 TRUE。 调用失败时，服务器将返回更准确的错误消息。|  
|`properties`|包含服务器存在的结构的子集。 使所有项将都删除。|  
  
## <a name="remarks"></a>注释  
 属性具有相同的数据类型作为`CreateEx`或`UpdateEx`方法的此组件接口; 但是，只有键的值很重要。 非键值将被忽略。 密钥的值必须与那些在服务器上进行匹配，否则将引发异常。  
  
 下面演示了如何使用密钥的值。 如果集合包含的项：  
  
-   item0  
  
-   item1  
  
-   item2  
  
-   item3  
  
 通过提供 item1 和 item3 属性中的密钥，可以删除 item1 和 item3:  
  
-   item1  
  
-   item3  
  
 在调用后，服务器集合中具有的剩余的项：  
  
-   item0  
  
-   item2  
  
 第二个示例显示包含其他集合的项：  
  
-   item0  
  
    -   item0a  
  
-   item1  
  
    -   item1a  
  
    -   item1b  
  
    -   item1c  
  
-   item2  
  
    -   item2a  
  
    -   item2b  
  
 可以通过从而键提供对 item1b 及 item2 删除 item1b 及其所有 item2:  
  
-   item1  
  
    -   item1b  
  
-   item2  
  
 通过提供 item2 空子集合，你将其转换叶和删除该整个子分支。 在调用后，服务器具有的剩余的项：  
  
-   item0  
  
    -   item0a  
  
-   item1  
  
    -   item1a  
  
    -   item1c  
  
## <a name="see-also"></a>另请参阅  
 [附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)