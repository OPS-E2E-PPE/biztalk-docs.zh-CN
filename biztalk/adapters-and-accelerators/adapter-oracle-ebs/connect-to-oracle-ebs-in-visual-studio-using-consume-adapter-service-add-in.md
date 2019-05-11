---
title: 连接到 Visual Studio 中使用适配器服务外接程序使用 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62d60216-5065-4048-b073-8618b7685e00
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66e0962ba33606129b3ac6a6747a75fa5ca2bf4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375608"
---
# <a name="connect-to-oracle-e-business-suite-in-visual-studio-using-consume-adapter-service-add-in"></a>连接到 Visual Studio 中使用适配器服务外接程序使用 Oracle E-business Suite
[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]安装时安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]加载在计算机上安装的所有 WCF 自定义绑定。 若要连接到使用基于 WCF 的 Oracle E-business Suite[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]在 BizTalk 项目中，必须使用**oracleEBSBinding**。  

 本主题说明了如何使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  

## <a name="connecting-to-oracle-e-business-suite-using-the-consume-adapter-service-add-in"></a>连接到 Oracle E-business Suite 使用使用适配器服务外接程序  
 执行以下步骤连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  

#### <a name="to-connect-to-oracle-e-business-suite"></a>若要连接到 Oracle E-business Suite  

1. 若要使用连接[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]BizTalk 解决方案中：  

   1. 创建 BizTalk 项目使用 Visual Studio。  

   2. 右键单击解决方案资源管理器中的项目，指向**外**，然后单击**添加生成的项**。  

   3. 在中**添加生成的项**对话框框中，执行以下操作：  


      |    使用此选项    |             执行的操作             |
      |----------------|------------------------------------|
      | **类别** | 单击**使用适配器服务**。 |
      | **模板**  | 单击**使用适配器服务**。 |


   4. 单击 **“添加”**。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]随即打开。  

2. 从**选择绑定**下拉列表中，选择**oracleEBSBinding**然后单击**配置**。  

3. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 Oracle E-business Suite。  


   |                                         使用此选项                                          |                                                                                                                                               执行的操作                                                                                                                                                |
   |-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                     **若要使用 Oracle 数据库凭据进行连接**                      |                                                                          指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。                                                                          |
   |                 **若要使用 Oracle E-business Suite 凭据进行连接**                  | 指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**并**OraclePassword**绑定属性。 |
   | **如果将 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**  |                                                                                                         指定的"/"对于**用户名**文本框中，保留**密码**文本框保留为空。                                                                                                         |
   | **如果将 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接** |                                       指定用于 Oracle E-business Suite 凭据**用户名**并**密码**文本框。 您还必须指定"/"作为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。                                       |


4. 单击**URI 属性**选项卡，并指定连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[创建的 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)。  

   > [!NOTE]
   >  如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。 但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  

5. 单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  

6. 单击“确定” 。  

7. 单击 **“连接”**。 建立连接后，连接状态显示为**已连接**。  

    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。  

    ![使用适配器服务对话框](../../adapters-and-accelerators/adapter-oracle-ebs/media/6a2b21ed-0fd2-4874-a6a6-e59a467533f8.gif "6a2b21ed-0fd2-4874-a6a6-e59a467533f8")  

    [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含在 Oracle E-business Suite 和 Oracle 数据库执行的各种操作的不同节点。 元数据的各种节点的分类方式的详细信息，请参阅[连接到 Visual Studio 中使用添加适配器元数据向导中的 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md)。  

## <a name="see-also"></a>请参阅  
 [连接到在 Visual Studio 中的 Oracle 电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)   
 [连接到 Oracle E-business Suite 使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)