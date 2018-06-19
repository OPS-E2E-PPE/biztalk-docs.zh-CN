---
title: 步骤 1： 用于调用 RFC 修改 vPrev BizTalk 项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, modifying previous version of BizTalk project for invoking an RFC
- migration
ms.assetid: 2d4a6cd7-d216-4e0f-8f82-41e044cd325b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f967a268d8baca3ab12f29bbac4b9eccc3cd75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218101"
---
# <a name="step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc"></a>步骤 1： 用于调用 RFC 修改 vPrev BizTalk 项目
![步骤 1，共 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 向现有 vPrev BizTalk 项目在此步骤中，进行以下更改：  
  
-   为使用基于 WCF 的 SD_RFC_CUSTOMER_GET RFC 生成元数据[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
-   用于调用的调用使用基于 WCF 的 RFC 使用请求消息的 vPrev SAP 适配器的 RFC 将请求消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
-   将使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到 vPrev SAP 适配器的响应消息。  
  
## <a name="prerequisite"></a>前提条件  
  
-   你必须具有 vPrev BizTalk 项目来调用 SD_RFC_CUSTOMER_GET RFC SAP 系统中。  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>若要修改 vPrev BizTalk 项目  
  
1.  为使用基于 WCF 的 SD_RFC_CUSTOMER_GET RFC 生成元数据[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 你可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成的元数据。  
  
     有关如何为 Rfc 生成元数据的说明，请参阅[浏览、 搜索和 get 元数据在 SAP 中的 RFC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)。 生成架构后，其名称类似于文件*SapBindingSchema.xsd*添加到 BizTalk 项目。 此文件包含用于调用使用基于 WCF 的 SD_RFC_CUSTOMER_GET 架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
2.  为 SD_RFC_CUSTOMER_GET RFC 生成元数据还会创建端口绑定文件。 在下一步的步骤中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 SAP 系统。 该操作的 SOAP 操作也设置为其生成元数据的操作。 例如，如果为 SD_RFC_CUSTOMER_GET RFC 生成元数据，则在发送端口上的 SOAP 操作中的操作名称将"SD_RFC_CUSTOMER_GET"。 但是，该操作将在你为业务流程的一部分可能不同，例如，创建的逻辑发送端口上"Operation_1"。 结果是，当消息发送到使用发送端口的 SAP 系统时，你将收到错误。 若要防止此情况，请确保发送端口业务流程中的是为其生成元数据的操作名称相同的逻辑上的操作名称。  
  
     因此，对于本教程中，由于为 SD_RFC_CUSTOMER_GET RFC 生成元数据，更改到"SD_RFC_CUSTOMER_GET"的逻辑发送端口操作的名称。  
  
3.  对于请求消息中，使用架构生成使用基于 WCF 的 vPrev SAP 适配器生成将架构映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
    1.  将 BizTalk 映射程序添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。  
  
         在**添加新项**对话框中，从左侧的窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定的名称映射，如**RequestMap.btm**。 单击 **“添加”**。  
  
    2.  从源架构窗格中，单击**打开源架构**。  
  
    3.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev SAP 适配器请求消息的架构。 对于本教程中，选择*SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*，然后单击**确定**。  
  
    4.  在**源架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GET_Request*，然后单击**确定**。  
  
    5.  从目标架构窗格中，单击**打开目标架构**。  
  
    6.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，并选择基于 WCF 的请求消息的架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 对于本教程中，选择*SAP_Migration.SapBindingSchema*，然后单击确定。  
  
    7.  在**目标架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GET*，然后单击**确定**。  
  
         下图中所示映射这两个架构中的相应元素。 将使用字符串左侧 Trim functoid CUSTOMER_T 元素的映射。 为此，请从**工具箱**，拖动**字符串左侧 Trim** functoid 并将其放映射器网格。 连接**CUSTOMER_T** functoid 源架构中的元素。 同样，连接**CUSTOMER_T** functoid 到目标架构中的元素。 下图说明了如何通过提取 functoid 映射的两个元素。  
  
         ![适配器版本之间的请求消息映射](../../adapters-and-accelerators/adapter-sap/media/f12f280d-766f-4647-bced-435354206fb9.gif "f12f280d-766f-4647-bced-435354206fb9")  
  
        > [!NOTE]
        >  有关字符串左侧 Trim functoid 的详细信息，请参阅"字符串左侧 Trim Functoid"网址[http://go.microsoft.com/fwlink/?LinkId=105774](http://go.microsoft.com/fwlink/?LinkId=105774)。  
  
    8.  保存映射。  
  
4.  响应消息中，使用架构生成使用基于 WCF 的 vPrev SAP 适配器生成将架构映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
    1.  将 BizTalk 映射程序添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。  
  
         在**添加新项**对话框中，从左侧的窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定的名称映射，如**ResponseMap.btm**。 单击 **“添加”**。  
  
    2.  从源架构窗格中，单击**打开源架构**。  
  
    3.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，并选择基于 WCF 的响应消息的架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 对于本教程中，选择*SAP_Migration.SapBindingSchema*，然后单击**确定**。  
  
    4.  在**源架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GETResponse*，然后单击**确定**。  
  
    5.  从目标架构窗格中，单击**打开目标架构**。  
  
    6.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev SAP 适配器的响应消息的架构。 对于本教程中，选择*SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*，然后单击**确定**。  
  
    7.  在**目标架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GET_Response*，然后单击**确定**。  
  
    8.  下图中所示映射这两个架构中的相应元素。  
  
         ![映射适配器版本之间的响应消息](../../adapters-and-accelerators/adapter-sap/media/d8dddaba-d978-4159-bcc6-6a6bfee36564.gif "d8dddaba-d978-4159-bcc6-6a6bfee36564")  
  
    9. 保存映射。  
  
5.  保存并生成 BizTalk 解决方案。 右键单击解决方案，并依次**生成解决方案**。  
  
6.  部署该解决方案。 右键单击解决方案，并依次**部署解决方案**。  
  
## <a name="next-steps"></a>后续步骤  
 创建 WCF 自定义发送端口，并将其配置为使用你在此步骤中创建的图中所述[步骤 2： 在 BizTalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程 2： 迁移 SAP RFC BizTalk 项目](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)