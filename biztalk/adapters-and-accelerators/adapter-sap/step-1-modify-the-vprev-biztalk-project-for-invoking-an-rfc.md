---
title: 第 1 步：修改 vPrev BizTalk 项目以调用 RFC |Microsoft Docs
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
ms.openlocfilehash: 6a9000f4754517223fe39856cdac9e50e2ab676c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372935"
---
# <a name="step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc"></a>第 1 步：修改 vPrev BizTalk 项目以调用 RFC
![3 的第 1 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **若要完成的时间：** 10 分钟。  
  
 **目标：** 在此步骤中，向现有 vPrev BizTalk 项目进行以下更改：  
  
- 为使用基于 WCF 的 SD_RFC_CUSTOMER_GET RFC 生成元数据[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
- 用于调用 RFC 调用使用基于 WCF 的在 RFC 使用 vPrev SAP 适配器添加到请求消息请求消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
- 使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到 vPrev SAP 适配器的响应消息。  
  
## <a name="prerequisite"></a>先决条件  
  
-   必须具有 vPrev BizTalk 项目以调用 SD_RFC_CUSTOMER_GET RFC，SAP 系统中。  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>若要修改 vPrev BizTalk 项目  
  
1. 为使用基于 WCF 的 SD_RFC_CUSTOMER_GET RFC 生成元数据[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成元数据。  
  
    有关如何为 Rfc 生成元数据的说明，请参阅[浏览、 搜索和获取 RFC 操作在 SAP 中的元数据](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)。 生成架构后，具有类似名称的文件*SapBindingSchema.xsd*添加到 BizTalk 项目。 此文件包含用于调用使用基于 WCF 的 SD_RFC_CUSTOMER_GET 架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
2. 正在为 SD_RFC_CUSTOMER_GET RFC 生成元数据还会创建端口绑定文件。 在下一步中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 SAP 系统。 该操作的 SOAP 操作也设置为其生成元数据的操作。 例如，如果为 SD_RFC_CUSTOMER_GET RFC 生成元数据，请在发送端口上的 SOAP 操作中的操作名称将"SD_RFC_CUSTOMER_GET"。 但是，该操作命名时创建的业务流程的一部分可能会有所不同，例如，在逻辑发送端口上"Operation_1"。 因此时将消息发送到 SAP 系统使用的发送端口，, 则会出错。 若要防止此情况，请确保发送端口在业务流程中的为其生成元数据的操作名称相同的操作名称上的逻辑。  
  
    因此，对于本教程中，由于为 SD_RFC_CUSTOMER_GET RFC 生成元数据，请更改到"SD_RFC_CUSTOMER_GET"的逻辑发送端口操作的名称。  
  
3. 请求消息映射使用 vPrev SAP 适配器添加到使用基于 WCF 的生成的架构生成的架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
   1. 将 BizTalk 映射器添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**外**，然后单击**新项**。  
  
       在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定映射的名称，如**RequestMap.btm**。 单击 **“添加”**。  
  
   2. 在源架构窗格中，单击**打开源架构**。  
  
   3. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择 vPrev SAP 适配器的请求消息的架构。 对于本教程中，选择*SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*，然后单击**确定**。  
  
   4. 在中**源架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GET_Request*，然后单击**确定**。  
  
   5. 从目标架构窗格中，单击**打开目标架构**。  
  
   6. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择的基于 WCF 的请求消息的架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 对于本教程中，选择*SAP_Migration.SapBindingSchema*，然后单击确定。  
  
   7. 在中**目标架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GET*，然后单击**确定**。  
  
       下图中所示映射这两个架构中的相应元素。 使用字符串左侧空格裁剪 functoid 将 CUSTOMER_T 元素映射。 为此，请从**工具箱**，拖动**字符串左侧空格裁剪**functoid 并将其放在映射器网格。 连接**CUSTOMER_T**至该 functoid 将源架构中的元素。 同样，连接**CUSTOMER_T** functoid 到目标架构中的元素。 下图说明了如何通过提取 functoid 映射的两个元素。  
  
       ![将在适配器各版本之间的请求消息映射](../../adapters-and-accelerators/adapter-sap/media/f12f280d-766f-4647-bced-435354206fb9.gif "f12f280d-766f-4647-bced-435354206fb9")  
  
      > [!NOTE]
      >  有关字符串左侧空格裁剪 functoid 的详细信息，请参阅"字符串左剪裁 ' Functoid"网址[ http://go.microsoft.com/fwlink/?LinkId=105774 ](http://go.microsoft.com/fwlink/?LinkId=105774)。  
  
   8. 保存该映射。  
  
4. 响应消息中，将映射生成使用 vPrev SAP 适配器添加到使用基于 WCF 的生成的架构的架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
   1. 将 BizTalk 映射器添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**外**，然后单击**新项**。  
  
       在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定映射的名称，如**ResponseMap.btm**。 单击 **“添加”**。  
  
   2. 在源架构窗格中，单击**打开源架构**。  
  
   3. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择的基于 WCF 的响应消息的架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 对于本教程中，选择*SAP_Migration.SapBindingSchema*，然后单击**确定**。  
  
   4. 在中**源架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GETResponse*，然后单击**确定**。  
  
   5. 从目标架构窗格中，单击**打开目标架构**。  
  
   6. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择 vPrev SAP 适配器的响应消息的架构。 对于本教程中，选择*SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*，然后单击**确定**。  
  
   7. 在中**目标架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GET_Response*，然后单击**确定**。  
  
   8. 下图中所示映射这两个架构中的相应元素。  
  
       ![映射响应消息在适配器各版本之间](../../adapters-and-accelerators/adapter-sap/media/d8dddaba-d978-4159-bcc6-6a6bfee36564.gif "d8dddaba-d978-4159-bcc6-6a6bfee36564")  
  
   9. 保存该映射。  
  
5. 保存并生成 BizTalk 解决方案。 右键单击解决方案，然后依次**生成解决方案**。  
  
6. 部署解决方案。 右键单击解决方案，然后依次**部署解决方案**。  
  
## <a name="next-steps"></a>后续步骤  
 创建 WCF 自定义发送端口，并将其配置为使用在此步骤中创建的地图中所述[步骤 2:在 BizTalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程 2：迁移 SAP RFC BizTalk 项目](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)