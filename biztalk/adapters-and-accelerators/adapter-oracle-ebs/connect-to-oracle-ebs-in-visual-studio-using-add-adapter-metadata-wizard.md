---
title: 连接到 Visual Studio 中使用添加适配器元数据向导中的 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fadc722-0098-457e-a2e2-3e9cc96eab5e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eea516ca2fffb683c4c772ee7719b69edcc0662f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008814"
---
# <a name="connect-to-oracle-e-business-suite-in-visual-studio-using-add-adapter-metadata-wizard"></a>连接到 Oracle E-business Suite 在 Visual Studio 中使用添加适配器元数据向导
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还会显示为 BizTalk 适配器，因此，您可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]来为你想要使用的适配器 Oracle E-business Suite 上执行的操作生成架构。  

## <a name="connecting-to-oracle-e-business-suite-using-the-add-adapter-metadata-wizard"></a>连接到 Oracle E-business Suite 使用添加适配器元数据向导  
 执行以下步骤连接到 Oracle E-business Suite 使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

#### <a name="to-connect-to-oracle-e-business-suite"></a>若要连接到 Oracle E-business Suite  

1. 若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：  

   1. 创建 BizTalk 项目使用 Visual Studio。  

   2. 右键单击解决方案资源管理器中的项目，指向**外**，然后单击**添加生成的项**。  

   3. 在中**添加生成的项**对话框框中，执行以下操作：  


      |    使用此选项    |           执行的操作            |
      |----------------|---------------------------------|
      | **类别** |     单击**将适配器添加**。      |
      | **模板**  | 单击**添加适配器元数据**。 |


   4. 单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  

   5. 在中[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，选择**Wcf-oracleebs**。 选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。  

      > [!IMPORTANT]
      >  如果已配置 BizTalk 中的 WCF OracleEBS 端口，选择从端口**端口**列表。  

   6. 单击“下一步” 。  

2. 从**选择绑定**下拉列表中，选择**oracleEBSBinding**然后单击**配置**。  

3. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 Oracle E-business Suite。  


   |                                                                                           |                                                                                                                                                                                                                                                                                                         |
   |-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                         使用此选项                                          |                                                                                                                                               执行的操作                                                                                                                                                |
   |                     **若要使用 Oracle 数据库凭据进行连接**                      |                                                                          指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。                                                                          |
   |                 **若要使用 Oracle E-business Suite 凭据进行连接**                  | 指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**并**OraclePassword**绑定属性。 |
   | **如果将 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**  |                                                                                                         指定的"/"对于**用户名**文本框中，保留**密码**文本框保留为空。                                                                                                         |
   | **如果将 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接** |                                       指定用于 Oracle E-business Suite 凭据**用户名**并**密码**文本框。 您还必须指定"/"作为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。                                       |


4. 单击**URI 属性**选项卡，并指定连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[创建的 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md))。  

   > [!NOTE]
   >  如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。 但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  

5. 单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  

   > [!NOTE]
   >  如果您正在生成元数据中使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]并且选择了现有 WCF OracleEBS 发送端口，不需要指定绑定属性。 绑定属性是从发送端口配置中选取。 但是，您可以选择指定如果任何，则需要在设计时的绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定的发送端口配置中的绑定属性的值将适用。  

6. 单击“确定” 。  

7. 单击 **“连接”**。 建立连接后，连接状态显示为**已连接**。  

    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。  

    ![使用适配器服务对话框](../../adapters-and-accelerators/adapter-oracle-ebs/media/6a2b21ed-0fd2-4874-a6a6-e59a467533f8.gif "6a2b21ed-0fd2-4874-a6a6-e59a467533f8")  

    [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含在 Oracle E-business Suite 和 Oracle 数据库执行的各种操作的不同节点。 元数据的各种节点的分类方式的详细信息，请参阅[连接到 Visual Studio 中使用添加适配器元数据向导中的 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md)。  

## <a name="see-also"></a>请参阅  
 [连接到在 Visual Studio 中的 Oracle 电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)   
 [连接到 Oracle E-business Suite 使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)