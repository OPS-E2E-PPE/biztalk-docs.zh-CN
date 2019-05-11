---
title: 连接到 Visual Studio 中使用添加适配器元数据向导中的 Oracle 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 726b3f82-887c-407a-bb9f-dcb9443155b0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9363a85c59c88b4998155941654149250a631ca4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376682"
---
# <a name="connect-to-oracle-database-in-visual-studio-using-add-adapter-metadata-wizard"></a>连接到 Oracle 数据库，在 Visual Studio 中使用添加适配器元数据向导
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]还会显示为 BizTalk 适配器，因此，您可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]来为你想要使用该适配器在 Oracle 数据库上执行的操作生成架构。  

 本主题说明了如何使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

## <a name="connecting-to-an-oracle-database-using-the-add-adapter-metadata-wizard"></a>连接到 Oracle 数据库使用添加适配器元数据向导  
 执行以下步骤连接到 Oracle 数据库使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

#### <a name="to-connect-to-an-oracle-database"></a>若要连接到 Oracle 数据库  

1. 若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：  

   1. 右键单击解决方案资源管理器中的项目，指向**外**，然后单击**添加生成的项**。  

   2. 在中**添加生成的项**对话框框中，执行以下操作：  


      |    使用此选项    |           执行的操作            |
      |----------------|---------------------------------|
      | **类别** |     单击**将适配器添加**。      |
      | **模板**  | 单击**添加适配器元数据**。 |


   3. 单击 **“添加”**。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]随即打开。  

   4. 在添加适配器元数据向导中，选择**Wcf-oracledb**。 选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。  

      > [!IMPORTANT]
      >  如果已在 BizTalk 中配置的 Wcf-oracledb 端口，选择从端口**端口**列表。  

   5. 单击“下一步” 。  

2. 从**选择绑定**下拉列表中，选择**oracleDBBinding**然后单击**配置**。  

3. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 Oracle 数据库。  

   1. 若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。 请确保指定的用户名和密码以连接到 Oracle 数据库时遵循以下注意事项：  

      - **用户名称**。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的用户名的值的大小写。 对 Oracle 数据库用户名称是区分大小写。 应确保提供 Oracle 用户名称[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在所需的 Oracle 数据库的情况下。 通常情况下，这意味着在 SCOTT/TIGER 凭据的用户名称应为大写："SCOTT"。  

      - **密码**。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的密码值的大小写。 对于发行版 10g 和更早版本，不区分大小写上 Oracle 系统的密码。  

   2. 若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。  

4. 单击**URI 属性**选项卡，并指定连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  

5. 单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。 例如，如果你想要面向 POLLINGSTMT 操作，则必须设置**PollingStatement**属性绑定。 有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。

   > [!NOTE]
   >  如果您正在生成元数据中使用添加适配器元数据向导并选择现有 Wcf-oracledb 发送端口，则需要指定的绑定属性。 绑定属性是从发送端口配置中选取。 但是，您可以选择指定如果任何，则需要在设计时的绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定的发送端口配置中的绑定属性的值将适用。  

6. 单击“确定” 。  

7. 单击 **“连接”**。 建立连接后，连接状态显示为**已连接**。  

    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。  

    ![使用适配器服务连接对话框](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")  

## <a name="see-also"></a>请参阅  
 [连接到 Oracle 数据库，在 Visual Studio 中使用添加适配器服务引用](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md)   
 [连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)