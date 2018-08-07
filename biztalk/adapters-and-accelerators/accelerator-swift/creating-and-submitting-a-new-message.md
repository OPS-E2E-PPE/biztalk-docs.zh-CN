---
title: 创建和提交新消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, messages
- submitting, messages
- messages, submitting
- messages, creating
ms.assetid: 88b7a2d3-44a4-44e4-ba8c-527c10290925
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbaef31e6bf47538e57b4c509efcb7a8cf565162
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970094"
---
# <a name="creating-and-submitting-a-new-message"></a>创建和提交新消息
本部分介绍如何提交新消息。 作为修复后的消息，使用新的消息必须验证和批准的消息创建者以外的人员。  

 若要提交新消息，您必须上载到新的 SWIFT 消息文档库的你想要提交的消息类型的消息模板文件。 手动上传的单个消息模板，也可以上载使用 FormPublish 工具的所有消息模板。  

### <a name="to-upload-a-single-message-template-into-the-new-document-library"></a>若要将单个消息模板上传到新的文档库  

1.  请参阅部分[窗体生成器实用程序生成 MT/MX InfoPath 表单](../../adapters-and-accelerators/accelerator-swift/form-generator-utility-to-generate-mt-mx-infopath-forms.md)有关的说明。  

### <a name="to-create-and-submit-a-new-message"></a>若要创建和提交新消息  

1. 在 Internet Explorer 中，打开你的 MRSR 站点置于 http://localhost/sites/bassite 。  

2. 单击**文档**，然后单击**新 SWIFT 消息**。  

3. 在新的 SWIFT 消息页上，双击包含你想要创建的消息类型的类别的名称。  

4. 单击你想要创建的消息的窗体模板。  

5. 在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]2007年窗口中的，消息中窗体中，所有必填的字段 （作为由星号表示） 和你想要使用的任何可选字段的类型消息数据。  

6. 若要查找 BIC、 当前角色中： 创建窗格，请单击**BIC 查找**。  

7. 键入的金融机构、 bank 代码和国家/地区的名称，然后单击**搜索**。  

8. BIC 查找窗格中，将 BIC 复制到消息窗体中的相应的银行代码字段。  

9. 在当前角色中： 创建窗格，请单击**验证**，然后单击**验证消息**。  

10. 在当前角色的结果窗格中： 创建窗格中，确定需要在消息中修复的错误。  

    > [!NOTE]
    >  如果修复所有验证错误消息中，您只能提交一封新邮件。  

11. 从顶部窗口的标准工具栏中，单击**提交**。  

12. 在用于选择证书来签署该窗体数字签名向导页上，选择你想要使用表单 （为创建者创建的证书） 进行签名的证书。 单击**查看证书**如果你想要验证是否使用正确的签名。 单击“下一步” 。  

    > [!NOTE]
    >  若要验证数字签名的有效性，请单击**数字签名**上**工具**菜单中，单击你想要验证，，然后单击的数字签名**查看签名窗体**.  

13. 在用于输入注释数字签名向导页上，单击**完成**。  

14. 在验证窗体数字签名向导页上，验证签名的消息正确。 单击**查看证书**如果你想要验证是否使用正确的签名。 单击**我已在签名之前验证此内容**，然后单击**登录**。  

15. 在验证数字签名窗口中，单击**关闭**。  

16. 在提交成功对话框中，单击**确定**。  

17. 关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。
