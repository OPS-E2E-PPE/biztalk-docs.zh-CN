---
title: DeleteOnly 方法 |Microsoft Docs
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
ms.openlocfilehash: bf006e4ba2db1378a207c4e20136310b6977c928
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352276"
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
|`key`|是一组必须提供的参数。 此项集必须存在于服务器数据库中，否则将出错。 为特定组件接口定义，这些项对应于 Get 关键字组。|  
|`correctionMode`|一个布尔型标志。 何时设置为 true，允许集合中的过去的有效日期项删除。 具体而言，它允许在当前的生效日期之前具有 EFFDT 的项目的删除。 如果没有此标志设置为 TRUE，对这些项的任何修改会导致从 PeopleSoft 服务器返回错误。 **注意：** `correctionMode`参数仅公开为这些组件接口，即包含有效日期项。 否则它不会显示作为参数的一部分。|  
|`interactiveMode`|用于错误处理。<br /><br /> 访问组件接口中的属性时，用于 PeopleSoft Enterprise 的 BizTalk 适配器使用 PeopleSoft 提供的 Api，它读取和写入组件接口; 中的各个字段但是，这些更改将不会传播到 PeopleSoft 服务器一次。 相反，psjoa.jar （与用于 PeopleSoft Enterprise 的 BizTalk 适配器进行交互） 包的所有更改，并将所做的更改发送到一个包中的服务器。 如果任何单个更新失败，一般会返回错误，这不会不找出实际的错误。 将交互模式设置为 TRUE 时，每个字段更新为发送到服务器单独。 这对性能，有重大影响，但如果更新失败 （例如，如果无效的值用于设置的字段） 提供特定错误的信息。<br /><br /> `interactiveMode`参数提供最佳性能，并提供错误报告字段更新级别。 若要正确使用此功能，建议进行常规调用`interactiveMode`设置为 FALSE。 在性能上应该有任何影响。 如果返回错误，则相同的调用可以重试 interactiveMode 标志设置为 TRUE。 当调用失败时，服务器将返回更精确的错误消息。|  
|`properties`|包含在服务器存在的结构的一部分。 删除保留的所有项。|  
  
## <a name="remarks"></a>备注  
 属性具有相同的数据类型为`CreateEx`或`UpdateEx`方法的此组件接口; 但是，只有密钥值非常重要。 非密钥值将被忽略。 键值必须与服务器上的匹配，否则会引发的异常。  
  
 下面演示了如何使用密钥值。 如果集合包含的项：  
  
- item0  
  
- item1  
  
- item2  
  
- item3  
  
  可以通过提供 item1 和 item3 属性中的密钥删除 item1 和 item3:  
  
- item1  
  
- item3  
  
  调用后，服务器具有在集合中剩余项：  
  
- item0  
  
- item2  
  
  第二个示例显示包含其他集合的项：  
  
- item0  
  
  -   item0a  
  
- item1  
  
  -   item1a  
  
  -   item1b  
  
  -   item1c  
  
- item2  
  
  -   item2a  
  
  -   item2b  
  
  可以通过向密钥 item1b 和 item2 删除 item1b 及其所有 item2:  
  
- item1  
  
  -   item1b  
  
- item2  
  
  通过提供 item2 空子集合，其转变为一个叶和删除的整个子分支。 在调用后，服务器有剩余的项目：  
  
- item0  
  
  -   item0a  
  
- item1  
  
  -   item1a  
  
  -   item1c  
  
## <a name="see-also"></a>请参阅  
 [附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)