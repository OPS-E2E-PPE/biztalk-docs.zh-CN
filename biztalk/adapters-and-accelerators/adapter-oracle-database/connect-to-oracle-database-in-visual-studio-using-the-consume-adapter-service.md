---
title: 连接到 Oracle 数据库，在 Visual Studio 中使用使用适配器服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connecting, to the Oracle database
- connection, to the Oracle database
ms.assetid: db2789d0-2d61-472b-ad0c-4ef0707e9c64
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19e83b518e188528b357e52f6397045baeb3ed76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010472"
---
# <a name="connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service"></a>连接到 Visual Studio 中使用使用适配器服务中的 Oracle 数据库
使用适配器服务外接程序被安装在安装 WCF LOB 适配器 SDK 时。 使用适配器服务外接程序加载的计算机上安装的所有 WCF 自定义绑定。 若要连接到使用基于 WCF 的 Oracle 数据库[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在 BizTalk 项目中，必须使用**oracleDBBinding**。  

 本主题将说明了如何使用适配器服务外接程序使用。  

## <a name="connecting-to-an-oracle-database-using-the-consume-adapter-service-add-in"></a>连接到 Oracle 数据库使用使用适配器服务外接程序  
 执行以下步骤连接到 Oracle 数据库使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  

1. 若要使用连接[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]BizTalk 解决方案中：  

   1. 右键单击解决方案资源管理器中的项目，指向**外**，然后单击**添加生成的项**。  

   2. 在中**添加生成的项**对话框框中，执行以下操作：  


      |    使用此选项    |             执行的操作             |
      |----------------|------------------------------------|
      | **类别** | 单击**使用适配器服务**。 |
      | **模板**  | 单击**使用适配器服务**。 |


   3. 单击 **“添加”**。 此时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会打开。  

2. 从**选择绑定**下拉列表中，选择**oracleDBBinding**然后单击**配置**。  

3. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 Oracle 数据库。  

   1. 若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。 请确保指定的用户名和密码以连接到 Oracle 数据库时遵循以下注意事项：  

      - **用户名称**。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的用户名的值的大小写。 对 Oracle 数据库用户名称是区分大小写。 应确保提供 Oracle 用户名称[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在所需的 Oracle 数据库的情况下。 通常情况下，这意味着在 SCOTT/TIGER 凭据的用户名称应为大写:"SCOTT"。  

      - **密码**。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的密码值的大小写。 对于发行版 10g 和更早版本，不区分大小写上 Oracle 系统的密码。  

   2. 若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。  

4. 单击**URI 属性**选项卡，并指定连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  

5. 单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。 例如，如果你想要面向 POLLINGSTMT 操作，则必须设置**PollingStatement**属性绑定。 有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  

6. 单击“确定” 。  

7. 单击 **“连接”**。 建立连接后，连接状态显示为**已连接**。  

    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。  

    ![使用适配器服务连接对话框](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")  

## <a name="see-also"></a>请参阅  
 [连接到 Oracle 数据库，在 Visual Studio 中使用添加适配器服务引用](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md)   
 [连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)