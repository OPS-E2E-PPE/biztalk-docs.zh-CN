---
title: "故障排除 BAM |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e63299a8-5c74-4337-ba20-3213e0c6ea1f
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d47932ffd9f7843d0b3d95073ca54bce987b8f75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-bam"></a>故障排除 BAM
本主题提供了帮助你解决使用业务活动监视 (BAM) 时可能遇到的问题的信息。  
  
## <a name="bam-deployment-failed"></a>BAM 部署失败  
 如果在 SQL Server Analysis Services 不可用时尝试部署包含实时聚合 (RTA) 的 BAM 定义，则 Bm.exe 命令将显示以下消息：  
  
 错误： BAM 部署失败。 无法进行连接。 请确保服务器正在运行。 无法建立连接，因为目标计算机主动拒绝 *\<IP 地址 >*。  
  
 出现这种情况的原因是，SQL Server Analysis Services 必须已经安装和配置，并且必须正在运行才能部署包含 RTA 的 BAM 定义。  
  
## <a name="cannot-refresh-the-live-data-workbook"></a>无法刷新实时数据工作簿  
 当你尝试在实时数据工作簿中刷新数据时，Microsoft Office Excel 可能会显示以下错误：  
  
 `XML for Analysis parser: The CurrentCatalog XML/A property was not specified.`  
  
 出现这种情况是因为尚未将 BAM 加载项添加到 Excel。  
  
#### <a name="to-add-the-bam-add-in-to-excel"></a>向 Excel 添加 BAM 加载项  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft Office**，然后单击**Microsoft Office Excel**。  
  
2.  单击**Microsoft Office 按钮**，然后单击**Excel 选项**。  
  
3.  在**Excel 选项**对话框中，单击**外接程序**。  
  
4.  在**外接程序**窗格中，单击**转**。  
  
5.  在**外接程序**对话框中，选择**业务活动监视**复选框，并依次**确定**。  
  
     ![添加 &#45; 单元对话框中](../core/media/addins.gif "外接程序")  
  
## <a name="errorobject-library-invalid-or-contains-references-to-object-definitions-that-could-not-be-found-with-bam-excel-add-in-in-office"></a>Office 中的 BAM Excel 加载项出现错误：“对象库无效或包含对无法找到的对象定义的引用”  
 在升级 Microsoft Excel 后尝试使用 BAM Excel 加载项时，可能会出现此错误。  
  
 **解决方法：**由于 BAM 外接程序使用 ActiveX 控件，你必须从以下目录中删除任何缓存的.exd 文件：  
  
-   C:\Documents and Settings\\< 用户名\>\Application Data\Microsoft\Forms  
  
-   C:\Documents and Settings\\< 用户名\>\AppData\Local\Temp\VBE  
  
## <a name="bam-portal-cannot-connect"></a>BAM 门户无法连接  
 在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] 中，你必须以管理员身份运行 BAM 门户。  
  
#### <a name="to-run-the-bam-portal-on-windows-server-2008-r2-or-windows-7"></a>在 Windows Server 2008 R2 或 Windows 7 上运行 BAM 门户  
  
1.  单击**启动**，指向**所有程序**，右键单击**Internet Explorer**，然后单击**以管理员身份运行**。  
  
2.  在**用户帐户控制**对话框中，单击**继续**。  
  
3.  在 Internet Explorer 地址栏中，键入`http://<server>/BAM`，其中*\<服务器 >*是运行 BAM 门户的计算机的名称。  
  
## <a name="bam-portal-does-not-work-if-invalid-users-are-granted-permissions"></a>如果向无效用户授予权限，BAM 门户则不起作用  
 如果将具有 BAM 查看权限的 AD 用户从 AD 中删除，则 BAM 门户不会为任何用户正确加载（DBO 除外）。  
  
 要解决此问题，请将无效用户从相应的 bam_{viewname}view 安全角色中删除。   
  
## <a name="cannot-export-or-import-a-bam-definition-to-localhost"></a>无法将 BAM 定义导出到 localhost 或从中导入  
 将 BAM 定义导出为 XML 时，如果尝试导出到 localhost，将看到以下错误消息：  
  
 `The system cannot find the path specified.`  
  
 不支持将 BAM 定义导出到 localhost。 同样，不支持从 localhost 导入 BAM 定义。  
  
## <a name="alerts-do-not-work-after-upgrading-sql-server-editions"></a>升级 SQL Server 版本后警报不再工作  
 如果已从 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的一个版本升级到另一个版本（例如，从标准版到企业版），将不会重新启动 BAM 警报。 若要解决此问题，请删除 BAM 警报并重新创建这些警报，或者升级 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 通知服务。  
  
#### <a name="to-upgrade-the-sql-server-notification-service"></a>升级 SQL Server 通知服务  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2005**，然后单击**通知服务命令提示符**。  
  
2.  在命令提示符下键入以下命令：  
  
     `nscontrol.exe upgrade -name <instanceName>`  
  
## <a name="objectdisposedexception-exception"></a>ObjectDisposedException Exception  
 如果你的应用程序使用 BAM WF 3.5 拦截器，你可能会收到以下错误消息： **System.ObjectDisposedException： 无法访问已释放的对象**。 有关此错误消息的详细信息，请参阅[ObjectDisposedException 异常](http://go.microsoft.com/fwlink/?LinkID=195338)(http://go.microsoft.com/fwlink/?LinkID=195338)。   
若要解决此问题，安装修补程序在 960754 [http://go.microsoft.com/fwlink/?LinkID=195339](http://go.microsoft.com/fwlink/?LinkID=195339)。  
  
## <a name="workbook-has-lost-its-vba-project-activex-controls-and-other-programmability-related-features"></a>工作簿丢失了其 VBA 项目、ActiveX 控件及其他与可编程序相关的功能  
 当尝试在 Microsoft Excel 中使用 BAM.xla 时, 可能会收到以下错误：  
  
 `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`  
  
 若要解决此问题，安装**应用程序的 Visual Basic**选项下**Office 共享功能**使用 Microsoft Office。  
  
## <a name="pivot-table-fails-to-get-the-data"></a>透视表无法获取数据  
 你拥有对 BAM 数据库的访问权限和角色，也拥有对所部署的视图的权限。 “活动搜索”页正常工作，你可以查看数据。 但是，在透视表中，会显示以下错误：  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* The following system error occurred:  No connection could be made because the target machine actively refused it.  
```  
  
 要解决此问题，请按照以下方式添加各个 DNS 设置：  
  
1.  单击**启动**并转到**控制面板**。  
  
2.  单击**网络和 Internet** ，然后单击**网络连接**。  
  
3.  （如本地区域连接中） 的网络连接上右键单击并选择**属性**。  
  
4.  上**本地区域连接**页上，选择**Internet 协议版本 4 (TCP/IPv4)**，然后单击**属性**。  
  
5.  单击 **“高级”**。 上**高级 TCP/IP 设置**页上，单击**DNS**选项卡。  
  
6.  选择**追加这些 DNS 后缀**，然后添加必需的 DNS 后缀。  
  
7.  单击**确定**并关闭所有打开的窗口。  
  
## <a name="pivot-table-view-shows-all-values-as-0"></a>透视表视图将所有值均显示为“0”  
 部署 BAM 门户后，“活动搜索”页将显示预期的结果。 但是，透视表视图将所有值均显示为“0”。 将显示以下错误：  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* Safety settings on this machine prohibit accessing a data source on another domain.  
```  
  
 要解决此问题，请按照以下方式将站点添加到区域：  
  
1.  在 Internet Explorer 窗口中，单击**工具**，然后单击**Internet 选项**。 单击**安全**选项卡上，然后选择**受信任的站点**区域。  
  
2.  单击**自定义级别**设置区域的安全级别。  
  
3.  上**设置**页上，在**跨域访问数据源**选项，请单击**提示**。 系统会在组件要求此权限时提示你。  
  
## <a name="see-also"></a>另请参阅  
 [使用业务活动监视](../core/using-business-activity-monitoring.md)