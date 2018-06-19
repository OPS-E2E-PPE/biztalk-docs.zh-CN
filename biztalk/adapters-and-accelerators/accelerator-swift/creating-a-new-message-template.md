---
title: 创建新的消息模板 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, templates
- templates, creating
- creating, templates
ms.assetid: 8c601d2b-b7a5-4ac4-9d98-fd9960038340
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a15e1c2a59635ca653e5a4817f29cdc918dca09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209237"
---
# <a name="creating-a-new-message-template"></a>创建新的消息模板
你可以从现有模板创建新的邮件模板。 这样，在自定义表单，例如一份已向其中输入一些数据的标准 SWIFT 窗体上创建新的消息实例的创建者。 使用新的模板，创建者不必输入所有所需使用空的窗体时的数据。  
  
 从消息实例已生成使用对应的现有模板创建新的模板。 将数据添加到的字段[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体 （就像你已创建的新消息实例），然后将窗体保存为新模板。  
  
### <a name="to-save-a-modified-existing-template-as-a-new-template"></a>若要将修改后的现有模板另存为新的模板  
  
1.  在 Internet Explorer 中，打开 http://localhost/sites/bassite MRSR 网站。  
  
2.  单击 **“文档”**。  
  
3.  在文档页上，单击**新 SWIFT MT 消息**文档库。  
  
4.  在新 SWIFT MT 消息页上，单击包含你想要使新模板基于模板的类别。  
  
5.  指向你想要根据你的新模板，单击右侧的箭头，然后单击该模板**在 Microsoft Office InfoPath 中编辑**。  
  
6.  在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]2007年窗口中，在消息表单中，输入你想要模板的一部分的消息数据。  
  
7.  单击**文件**，然后单击**另存为**。  
  
8.  在弹出窗口，该值指示窗体包含验证错误，单击**是**。  
  
9. 在另存为对话框中，选择中的模板的文件夹**将保存在**文本框中，然后再输入中的文件名**文件名**文本框。 单击 **“保存”**。  
  
10. 关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]新模板的表单。  
  
    > [!NOTE]
    >  若要从新的模板创建的消息实例，请参阅[创建和提交新消息](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)。