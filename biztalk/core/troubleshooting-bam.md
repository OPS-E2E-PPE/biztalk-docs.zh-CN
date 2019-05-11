---
title: BAM 疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e63299a8-5c74-4337-ba20-3213e0c6ea1f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d068b3f669400f2f7b55a3279aa40090adc8689f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243262"
---
# <a name="troubleshooting-bam"></a>BAM 问题疑难解答
本主题提供信息来帮助你解决问题时使用业务活动监视 (BAM) 可能会遇到。  
  
## <a name="bam-deployment-failed"></a>BAM 部署失败  
 如果尝试部署 SQL Server Analysis Services 不可用时包含实时聚合 (RTA) 的 BAM 定义，则 Bm.exe 命令将显示以下消息：  
  
 错误：BAM 部署失败。 无法进行连接。 请确保服务器正在运行。 无法建立连接，因为目标计算机主动拒绝 *\<IP 地址\>*。  
  
 这是因为 SQL Server Analysis Services 必须安装和配置，并且必须正在运行才能部署包含 RTA 的 BAM 定义。  
  
## <a name="cannot-refresh-the-live-data-workbook"></a>无法刷新实时数据工作簿  
 当您尝试刷新实时数据工作簿中的数据时，Microsoft Office Excel 可能会显示以下错误：  
  
 `XML for Analysis parser: The CurrentCatalog XML/A property was not specified.`  
  
 这是因为的 BAM 外接程序尚未添加到 Excel。  
  
#### <a name="add-the-bam-add-in-to-excel"></a>将添加到 Excel 的 BAM 外接程序  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft Office**，然后单击**Microsoft Office Excel**。  
  
2.  单击**Microsoft Office 按钮**，然后单击**Excel 选项**。  
  
3.  在中**Excel 选项**对话框中，单击**外接程序**。  
  
4.  在中**外接程序**窗格中，单击**转**。  
  
5.  在中**外接程序**对话框中，选择**业务活动监视**复选框，然后依次**确定**。  
  
     ![添加&#45;项对话框](../core/media/addins.gif "外接程序")  
  
## <a name="errorobject-library-invalid-or-contains-references-to-object-definitions-that-could-not-be-found-with-bam-excel-add-in-in-office"></a>错误:"对象库无效或包含对无法找到的对象定义的引用"与 BAM Excel 外接程序在 Office 中  
 尝试升级 Microsoft Excel 后，使用 BAM Excel 外接程序时，可能会收到此错误。  
  
 **解决方法：** 由于 BAM 外接程序使用的 ActiveX 控件，您必须从以下目录中删除缓存的.exd 文件：  
  
-   C:\Documents and Settings\\< 用户名\>data\microsoft\forms  
  
-   C:\Documents and Settings\\< 用户名\>\AppData\Local\Temp\VBE  
  
## <a name="bam-portal-cannot-connect"></a>BAM 门户无法连接  
以管理员身份运行 BAM 门户。  
  
#### <a name="run-the-bam-portal"></a>运行 BAM 门户
  
1.  单击**启动**，依次指向**所有程序**，右键单击**Internet Explorer**，然后单击**以管理员身份运行**。  
  
2.  在中**用户帐户控制**对话框中，单击**继续**。  
  
3.  在 Internet Explorer 地址栏中，键入`http://<server>/BAM`，其中*\<服务器\>* 是正在运行 BAM 门户的计算机的名称。  
  
## <a name="bam-portal-does-not-work-if-invalid-users-are-granted-permissions"></a>如果向无效用户授予权限 BAM 门户不起作用  
 如果从 AD 删除具有 BAM 查看权限的 AD 用户，然后在 BAM 门户未正常加载 （DBO 除外） 的任何用户。  
  
 若要解决此问题，请从相应的 bam_ {viewname} view 安全角色中删除无效的用户。  
  
## <a name="cannot-export-or-import-a-bam-definition-to-localhost"></a>不能导出或导入到 localhost 的 BAM 定义  
 以 XML 形式导出 BAM 定义时，将看到以下错误消息，如果你尝试将导出到 localhost:  
  
 `The system cannot find the path specified.`  
  
 不支持将 BAM 定义导出到 localhost。 同样，不支持从 localhost 导入 BAM 定义。  
  
## <a name="alerts-do-not-work-after-upgrading-sql-server-editions"></a>升级 SQL Server 版本后，警报不再工作。  
 如果已从一个版本的 SQL Server 升级到另一个版本 （例如，从标准版到企业版），将不重新启动 BAM 警报。 若要解决此问题，请删除 BAM 警报并重新创建它们，或升级 SQL Server 通知服务。  
  
#### <a name="upgrade-the-sql-server-notification-service"></a>升级 SQL Server 通知服务  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2005**，然后单击**通知服务命令提示符**。  
  
2.  在命令提示符下键入以下命令：  
  
     `nscontrol.exe upgrade -name <instanceName>`  
  
## <a name="objectdisposedexception-exception"></a>ObjectDisposedException 异常  
 如果你的应用程序使用 BAM WF 3.5 侦听器，可能会收到以下错误消息：**System.ObjectDisposedException:无法访问已释放的对象**。 有关此错误消息的详细信息，请参阅[ObjectDisposedException 异常](https://support.microsoft.com/help/960754)。 

若要解决此问题，请安装[修补程序 960754](https://support.microsoft.com/help/960754)。 
  
## <a name="workbook-has-lost-its-vba-project-activex-controls-and-other-programmability-related-features"></a>工作簿已丢失了其 VBA 项目、 ActiveX 控件和其他与可编程序相关功能  
 在尝试在 Microsoft Excel 中使用 BAM.xla 时，可能会收到以下错误：  
  
 `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`  
  
 若要解决此问题，请安装**应用程序的 Visual Basic**下**Office 共享功能**与 Microsoft Office。  
  
## <a name="pivot-table-fails-to-get-the-data"></a>数据透视表无法获取数据  
 部署的视图上有权访问 BAM 数据库，以及角色和权限。 活动搜索页上按预期方式工作，你可以看到数据。 但是，在数据透视表中，显示以下错误：  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* The following system error occurred:  No connection could be made because the target machine actively refused it.  
```  
  
 若要解决此问题，请添加各个 DNS 设置为如下所示：  
  
1.  单击**启动**并转到**控制面板**。  
  
2.  单击**网络和 Internet** ，然后单击**网络连接**。  
  
3.  右键单击网络连接 （如本地连接），然后选择**属性**。  
  
4.  上**本地连接**页上，选择**Internet 协议版本 4 (TCP/IPv4)**，然后单击**属性**。  
  
5.  单击 **“高级”**。 上**高级 TCP/IP 设置**页上，单击**DNS**选项卡。  
  
6.  选择**附加这些 DNS 后缀**，然后添加需要的 DNS 后缀。  
  
7.  单击**确定**并关闭所有打开的窗口。  
  
## <a name="pivot-table-view-shows-all-values-as-0"></a>数据透视表视图的所有值均都显示为"0"  
 在部署 BAM 门户时，活动搜索页将显示预期的结果。 但是，数据透视表视图显示的所有值为"0"。 将显示以下错误：  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* Safety settings on this machine prohibit accessing a data source on another domain.  
```  
  
 若要解决此问题，将站点添加到的区域，如下所示：  
  
1.  在 Internet Explorer 窗口中，单击**工具**，然后单击**Internet 选项**。 单击**安全**选项卡，然后选择**受信任的站点**区域。  
  
2.  单击**自定义级别**设置区域的安全级别。  
  
3.  上**设置**页面上，在**跨域访问数据源**选项，单击**提示**。 当一个组件需要此权限时，系统将提示您。  
  
## <a name="see-also"></a>请参阅  
 [使用业务活动监视](../core/using-business-activity-monitoring.md)