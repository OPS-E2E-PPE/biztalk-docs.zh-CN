---
title: 将连接到使用适配器服务外接程序中使用的 Visual Studio 中的 Oracle E-business Suite |Microsoft 文档
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
ms.openlocfilehash: 441c023d5a8bb83c1998a15cea065b88244209df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217149"
---
# <a name="connect-to-oracle-e-business-suite-in-visual-studio-using-consume-adapter-service-add-in"></a>将连接到使用适配器服务外接程序中使用的 Visual Studio 中的 Oracle E-business Suite
[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]安装时安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]加载在计算机上安装的所有 WCF 自定义绑定。 以连接到 Oracle E-business Suite 使用基于 WCF 的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]在 BizTalk 项目，你必须使用**oracleEBSBinding**。  
  
 本主题将说明了如何使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
## <a name="connecting-to-oracle-e-business-suite-using-the-consume-adapter-service-add-in"></a>连接到 Oracle E-business Suite 使用使用适配器服务外接程序  
 执行以下步骤以连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
#### <a name="to-connect-to-oracle-e-business-suite"></a>以连接到 Oracle E-business Suite  
  
1.  若要使用连接[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]BizTalk 解决方案中：  
  
    1.  创建 BizTalk 项目使用 Visual Studio。  
  
    2.  右键单击解决方案资源管理器中的项目，指向**添加**，然后单击**添加生成的项**。  
  
    3.  在**添加生成的项**对话框框中，执行以下操作：  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**类别**|单击**使用适配器服务**。|  
        |**模板**|单击**使用适配器服务**。|  
  
    4.  单击 **“添加”**。 此时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会打开。  
  
2.  从**选择的绑定**下拉列表中，选择**oracleEBSBinding**单击**配置**。  
  
3.  在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Oracle E-business Suite。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
    |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
    |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
    |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
4.  单击**URI 属性**选项卡，然后指定连接参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)。  
  
    > [!NOTE]
    >  如果连接参数包含任何保留的字符，则必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。 但是，如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。  
  
5.  单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。 有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
6.  单击 **“确定”**。  
  
7.  单击 **“连接”**。 建立连接后，连接状态将显示为**已连接**。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。  
  
     ![使用适配器服务对话框](../../adapters-and-accelerators/adapter-oracle-ebs/media/6a2b21ed-0fd2-4874-a6a6-e59a467533f8.gif "6a2b21ed-0fd2-4874-a6a6-e59a467533f8")  
  
     [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在 Oracle E-business Suite 和 Oracle 数据库执行的各种操作的不同节点。 在各种节点下的元数据的分类方式的详细信息，请参阅[连接到 Visual Studio 使用添加适配器元数据向导中的 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md)。  
  
## <a name="see-also"></a>另请参阅  
 [将连接到 Oracle E-business Suite Visual Studio 中](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)   
 [将连接到 Oracle E-business Suite 使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)