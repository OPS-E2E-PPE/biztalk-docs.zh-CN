---
title: 创建新的消息模板 |Microsoft Docs
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
ms.openlocfilehash: e89c34b29818ab053217b823c6f8a787ce50a15d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999830"
---
# <a name="creating-a-new-message-template"></a>创建新的消息模板
可以通过现有模板创建新的消息模板。 这使自定义窗体，如一份已向其中输入一些数据的标准 SWIFT 窗体上创建新的消息实例的创建者。 使用新的模板，创建者无需输入所有所需使用一个空窗体时的数据。  
  
 从具有使用相应的现有模板生成的消息实例创建一个新的模板。 将数据添加到字段的[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中 （如同你已创建新的消息实例），，然后将窗体保存为新模板。  
  
### <a name="to-save-a-modified-existing-template-as-a-new-template"></a>若要将已修改的现有模板另存为新的模板  
  
1. 在 Internet Explorer 中，打开你的 MRSR 站点置于http://localhost/sites/bassite。  
  
2. 单击 **“文档”**。  
  
3. 在文档页上，单击**新 SWIFT MT 消息**文档库。  
  
4. 在新 SWIFT MT 消息页上，单击包含你想要使新模板基于模板的类别。  
  
5. 指向你想要你的新模板基础，单击右侧的箭头，然后单击该模板**在 Microsoft Office InfoPath 中编辑**。  
  
6. 在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]2007年窗口中，在消息表单中，输入你想要将模板的一部分的消息数据。  
  
7. 单击**文件**，然后单击**另存为**。  
  
8. 在弹出窗口，该值指示窗体包含验证错误，单击**是**。  
  
9. 在另存为对话框中，选择的文件夹中的模板**将保存在**文本框中，并输入中的文件名**文件名**文本框。 单击 **“保存”**。  
  
10. 关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]新模板的窗体。  
  
    > [!NOTE]
    >  若要从新的模板创建消息实例，请参阅[创建和提交新消息](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)。