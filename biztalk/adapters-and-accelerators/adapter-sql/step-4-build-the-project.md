---
title: 步骤 4：生成项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d88b1407-ecdd-4dbf-90da-02dc4781568c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6216d96e0d9ce0f8e564fa45bc28c075ce124c8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367700"
---
# <a name="step-4-build-the-project"></a>步骤 4：生成项目
![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **若要完成的时间：** 5 分钟  
  
 **目标：** 在此步骤中，您将编译 BizTalk 业务流程项目。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成[步骤 3:发送要插入记录，并接收响应的请求消息](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)。  
  
### <a name="to-build-the-biztalk-orchestration-project"></a>若要生成 BizTalk 业务流程项目  
  
1. 在解决方案资源管理器，右键单击 BizTalk 项目名称，然后依次**属性**。  
  
2. 在属性页对话框中，在树窗格中，展开**常见属性**，单击**程序集**，然后在属性列表中，单击**程序集密钥文件**省略号 **[...]**.  
  
3. 指定创建中所述的程序集密钥文件的路径[创建 SQL 应用程序使用 SQL 适配器的先决条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)，然后单击**打开**。  
  
4. 在属性页对话框中，在树窗格中，展开**配置属性**，单击**部署**，然后执行以下操作：  
  
   1. 有关**应用程序名称**属性中，键入`SampleApplication`。  
  
   2. 有关**重新部署**属性中，选择**True**。  
  
      单击“确定” 。  
  
5. 在“文件”  菜单上，单击“全部保存” 。  
  
6. 在解决方案资源管理器，右键单击解决方案名称，然后单击**生成解决方案**。  
  
    在屏幕底部的输出窗格如下所示：**生成中：3 个成功或最新，0 失败，0 已跳过。**  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，您编译包含 BizTalk 项目和两个类库项目的解决方案。  
  
## <a name="next-steps"></a>后续步骤  
 在部署解决方案，如中所述[第 5 课：部署解决方案](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：发送要插入记录，并接收响应的请求消息](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)   
 [第 4 课：在采购订单表中执行插入操作](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)