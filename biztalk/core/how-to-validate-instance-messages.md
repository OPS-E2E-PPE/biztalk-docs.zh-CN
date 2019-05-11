---
title: 如何验证实例消息 |Microsoft Docs
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
ms.openlocfilehash: bb7d83c8ba847a84a38b2701bb5ca2492559d450
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333182"
---
# <a name="how-to-validate-instance-messages"></a>如何验证实例消息
构造架构之后，可以通过验证您知道此类实例消息的架构很好地反映现有实例消息中检查您的工作。  
  
 本主题提供执行此验证任务的分步说明。  
  
### <a name="to-validate-an-instance-message-against-a-schema"></a>若要验证针对架构的实例消息  
  
1.  在解决方案资源管理器，右键单击该架构，然后单击**属性**。  
  
2.  如有必要，在属性窗口中，展开**常规**一部分**常规**选项卡上，通过单击其加号 （+） 图标。  
  
3.  在中**输入实例文件名**属性值字段中，键入文件的名称，或使用省略号 (**...**) 按钮以浏览到包含要根据架构进行验证，然后单击的实例消息的文件的值字段右侧**打开**。  
  
4.  在中**解决方案资源管理器**，右键单击架构名称，然后单击**验证实例**。  
  
5.  在输出窗口中查看结果。 在此窗口中显示成功和错误消息。  
  
> [!NOTE]
>  有一些情况下实例中的特定架构生成消息可能无法通过使用该相同的架构进行验证。 有关这种情况下的详细信息，请参阅[架构生成和验证的已知问题](../core/known-issues-with-schema-generation-and-validation.md)。 通常情况下，想要编辑生成的实例消息并将更改，使其更真实地表示你的方案及其包含的数据。 然后使用此修改后的实例消息来验证您的架构。  
  
## <a name="see-also"></a>请参阅  
 [测试架构](../core/testing-schemas.md)   
 [架构验证](../core/schema-validation1.md)   
 [实例消息的生成和验证](../core/instance-message-generation-and-validation.md)