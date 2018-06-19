---
title: 从 SAP 使用 BizTalk Server 接收入站的 tRFC 调用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFC calls, receiving using BizTalk Server
- tRFCs, sample
ms.assetid: 500eedea-3d27-478c-a64c-903a1fa2b02f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 588e135507a2d186d9d8006836f5bdfb2940eb32
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962331"
---
# <a name="receive-inbound-trfc-calls-from-sap-using-biztalk-server"></a>从 SAP 使用 BizTalk Server 接收入站的 tRFC 调用
TRFC 服务器调用是事务的 RFC 服务器调用。 在事务上下文中接收 RFC 所需的业务流程是类似于业务流程以接收从某个 SAP 系统发送的任何其他入站的 RFC。 但是，你需要执行某些其他任务以确保在事务上下文中接收了 Rfc。 有关接收来自 SAP 系统使用的入站的 RFC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[SAP 使用 BizTalk Server 接收入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)。 有关详细信息，如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持入站的 tRFC 调用接收从 SAP 系统，请参阅[对 tRFCs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。  
  
 接收从某个 SAP 系统发送入站的 tRFC 是类似于接收入站的 RFC，具有以下差异：  
  
1.  在设计期间，时生成架构，请确保你选择从下的 tRFC **TRFC**节点。  
  
2.  在运行时，请确保您设置绑定属性**TidDatabaseConnectionString**。 此属性采用连接字符串以连接到 SQL 数据库来存储 TID。 一个连接字符串示例如下所示：  
  
    ```  
    Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
    ```  
  
     有关绑定属性以及如何将其设置的详细信息，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装向导安装 SQL 脚本，SapAdapter-DbScript-Install.sql，它必须运行的 SQL Server 管理员联系以在 SQL Server 中创建数据库和数据库对象。 该脚本通常安装在*\<安装驱动器\>： 程序 FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]* 。  
    >   
    >  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]用这些对象来持久保存 Tid。 因此，SQL Server 管理员必须确保用户名称提供连接字符串的一部分具有足够的特权执行存储的过程。 你也可以选择 Windows 身份验证提供的 Windows 用户具有足够的权限才能在数据库中执行存储的过程。  
  
3.  请确保在安装适配器的计算机上启用 MSDTC。 执行以下步骤以启用 MSDTC。  
  
    1.  组件服务 MMC 管理单元中启动。  
  
    2.  在组件服务 MMC 管理单元中，从左窗格中展开**组件服务**，展开**计算机**，右键单击**我的电脑**，然后单击**属性**。  
  
    3.  在**我的电脑属性**对话框中，单击**MSDTC**选项卡。  
  
    4.  在**事务配置**部分中，单击**安全配置**按钮。  
  
    5.  在**安全配置**对话框中，选择**网络 DTC 访问**复选框，在其中选择**允许远程客户端**复选框。  
  
    6.  在**事务管理器通信**部分中，选择**允许入站**和**允许出站**复选框。  
  
    7.  在**安全配置**对话框中，单击**确定**。  
  
    8.  单击**是**通知，将重新启动 MSDTC 服务对话框框中。 重新启动 MSDTC 服务后，单击**确定**在对话框中。  
  
    9. 在**我的电脑属性**对话框中，单击**确定**。  
  
4.  将 MSDTC 添加到 Windows 防火墙例外列表中，如果不是已添加。 运行以下命令。  
  
    ```  
    netsh firewall set allowedprogram %windir%\system32\msdtc.exe MSDTC enable  
    ```  
  
> [!IMPORTANT]
>  从 SAP 系统中的"事务性"上下文中接收到的 Idoc 时使用的入站的 tRFC 调用。  
  
## <a name="see-also"></a>另请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)