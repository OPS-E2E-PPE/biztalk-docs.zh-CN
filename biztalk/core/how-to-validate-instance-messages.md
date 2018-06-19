---
title: 如何验证实例消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f6302c6-b56b-4572-aa76-0f4c4599672a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd0baa898f801c924cffc5a446aa1a22d063a8fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256789"
---
# <a name="how-to-validate-instance-messages"></a>如何验证实例消息
在构造架构之后，通过根据该架构来验证已知的某个现有实例消息为此类实例消息的有效表示形式，可以检查您所做的工作。  
  
 本主题介绍了执行此验证任务的分步说明。  
  
### <a name="to-validate-an-instance-message-against-a-schema"></a>根据架构验证实例消息  
  
1.  在解决方案资源管理器，右键单击的架构，然后单击**属性**。  
  
2.  如有必要，在属性窗口中，展开**常规**部分**常规**选项卡上通过单击其加号 （+） 图标。  
  
3.  在**输入实例 Filename**属性值字段中，键入文件的名称，或者使用省略号 (**...**) 值字段来浏览文件包含实例消息以验证架构，然后单击右侧的按钮**打开**。  
  
4.  在**解决方案资源管理器**，右键单击架构名称，然后单击**验证实例**。  
  
5.  在“输出”窗口中，查看结果。 此窗口中将显示成功消息和错误消息。  
  
> [!NOTE]
>  在某些情况下，由特定架构生成的实例消息可能无法通过使用同一架构进行的验证。 有关这种情况下的详细信息，请参阅[已知架构生成和验证问题](../core/known-issues-with-schema-generation-and-validation.md)。 通常，您可能希望对生成的实例消息进行编辑并更改其包含的数据，以便该实例消息更实际地表示您的方案。 然后使用此修改的实例消息来验证您的架构。  
  
## <a name="see-also"></a>另请参阅  
 [测试架构](../core/testing-schemas.md)   
 [架构验证](../core/schema-validation1.md)   
 [实例消息生成和验证](../core/instance-message-generation-and-validation.md)