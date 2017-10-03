---
title: "创建和提交新消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, messages
- submitting, messages
- messages, submitting
- messages, creating
ms.assetid: 88b7a2d3-44a4-44e4-ba8c-527c10290925
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42cd2a82fe0ecde75446e68f9f58e17f103e5efa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-submitting-a-new-message"></a>创建和提交新消息
本部分介绍如何将提交一条新消息。 作为提供修复后的消息，一条新消息必须先验证并批准以外的消息创建者的人员。  
  
 若要提交新消息，你必须将上载到新 SWIFT 消息文档库你想要提交的消息的类型的消息模板文件。 你可以手动上载单个消息模板，也可以上载使用 FormPublish 工具的所有消息模板。  
  
### <a name="to-upload-a-single-message-template-into-the-new-document-library"></a>若要将单个消息模板上载到新的文档库  
  
1.  请参阅部分[窗体生成器实用程序生成 MT/MX InfoPath 窗体](../../adapters-and-accelerators/accelerator-swift/form-generator-utility-to-generate-mt-mx-infopath-forms.md)有关的说明。  
  
### <a name="to-create-and-submit-a-new-message"></a>若要创建并提交一条新消息  
  
1.  在 Internet Explorer 中，打开 http://localhost/sites/bassite MRSR 网站。  
  
2.  单击**文档**，然后单击**新 SWIFT 消息**。  
  
3.  在新 SWIFT 消息页上，双击包含想要创建的消息类型的类别的名称。  
  
4.  单击你想要创建的消息的表单模板。  
  
5.  在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]2007年窗口中的，消息中窗体中，类型 （作为用星号表示） 的所有必填的字段和任何可选字段，你想要使用的消息数据。  
  
6.  若要查找 BIC、 当前的角色中： 创建窗格中，请单击**BIC 查找**。  
  
7.  键入金融机构、 bank 代码和国家/地区的名称，然后单击**搜索**。  
  
8.  从 BIC 查找窗格中，将 BIC 复制到消息窗体中的相应的银行代码字段。  
  
9. 在当前角色： 创建窗格中，请单击**验证**，然后单击**Validate 消息**。  
  
10. 在结果窗格中的当前角色： 创建窗格中，确定需要在消息中修复的错误。  
  
    > [!NOTE]
    >  如果您没有固定的所有验证错误消息中，你仅可以提交一条新消息。  
  
11. 从窗口顶部标准工具栏中，单击**提交**。  
  
12. 在用于选择要对表单进行签名的证书数字签名向导页上，选择你想要使用表单 （你创建的创建者的证书） 进行签名的证书。 单击**查看证书**如果你想要验证是否正在使用正确的签名。 单击 **“下一步”**。  
  
    > [!NOTE]
    >  若要验证其有效性的数字签名，请单击**数字签名**上**工具**菜单上，单击你想要验证，，然后单击的数字签名**查看签名的表单**.  
  
13. 在用于输入注释数字签名向导页上，单击**完成**。  
  
14. 在验证窗体数字签名向导页上，验证将对进行签名的消息正确。 单击**查看证书**如果你想要验证是否正在使用正确的签名。 单击**我已在签名之前验证此内容**，然后单击**登录**。  
  
15. 在验证数字签名窗口中，单击**关闭**。  
  
16. 在提交成功对话框中，单击**确定**。  
  
17. 关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。