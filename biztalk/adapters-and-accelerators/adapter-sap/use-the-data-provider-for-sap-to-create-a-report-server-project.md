---
title: 使用适用于 SAP 的数据提供程序来创建报表服务器项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fe985b5-ba67-4179-a31c-4f41106c32be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45934085c75092f07264f8ed6fa4f9d6376ffbbb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372199"
---
# <a name="use-the-data-provider-for-sap-to-create-a-report-server-project"></a>使用适用于 SAP 的数据提供程序来创建报表服务器项目
必须创建报表服务器项目，使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，若要为 SAP 系统中可用的数据生成报表。 本主题将说明了如何创建报表服务器项目。  
  
## <a name="prerequisites"></a>先决条件  
 执行本主题中提供的过程之前，先确保已安装了[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]安装时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装。 有关详细信息[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，请参阅安装指南位于\<*安装驱动器*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。  
  
### <a name="to-create-a-report-server-project"></a>若要创建报表服务器项目  
  
1. 启动[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并创建一个报表服务器项目。 若要创建报表服务器项目，请执行以下操作：  
  
   1.  单击**文件**菜单上，单击**新建**，然后单击**项目**。  
  
   2.  在中**新的项目**对话框中，从**项目类型**列表中，选择**商业智能项目**。 从**Visual Studio 已安装的模板**列表中，选择**报表服务器项目**。  
  
   3.  指定的名称和项目的位置，然后单击**确定**。 对于本主题中，指定作为项目的名称`SAP_ Report`。  
  
2. 添加新的数据源：  
  
   1. 在解决方案资源管理器，右键单击**共享数据源**，然后单击**添加新数据源**。  
  
   2. 在中**共享数据源**对话框中**常规**选项卡上，指定数据源的名称。 有关本主题中，将名称指定为`SAPDataSource`。  
  
   3. 从**类型**列表中，选择**SAP 数据提供程序**。  
  
   4. 在中**连接字符串**框中，指定的连接字符串[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。 璝惠[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连接字符串，请参阅[了解数据提供程序类型适用于 SAP 连接字符串](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。  
  
       ![创建数据源](../../adapters-and-accelerators/adapter-sap/media/8494c1a5-5e68-4178-a005-a6ea56d97ad7.gif "8494c1a5-5e68-4178-a005-a6ea56d97ad7")  
  
      > [!NOTE]
      >  您可以选择指定的凭据作为连接字符串的一部分或下一步中所述指定它们。  
  
   5. 在中**凭据**选项卡上，选择下列选项之一，然后单击**确定**:  
  
      |使用此选项|执行的操作|  
      |--------------|----------------|  
      |**使用特定用户名和密码**|指定用户名和密码以连接到 SAP 系统。|  
      |**提示输入凭据**|生成报表时，SAP 系统的输入的凭据。 **注意：** 如果指定，作为连接字符串的一部分，此选项指定的凭据将覆盖凭据。|  
      |**无凭据**|如果你要作为连接字符串的一部分提供的用户名和密码，请选择此选项。|  
  
      > [!NOTE]
      >  报表服务器项目不支持 Windows 身份验证模式。  
  
3. 添加新报表：  
  
   1. 在解决方案资源管理器，右键单击**报表**，然后单击**添加新报表**。  
  
       这将启动报表向导。  
  
   2. 阅读欢迎屏幕上的信息，然后单击**下一步**。  
  
   3. 在中**选择数据源**对话框框中，选择**共享数据源**选项中，选择**SAPDataSource**您在上一步中创建，然后单击**下一步**。  
  
   4. 如果选择了**凭据提示**选项来创建数据源时指定的用户凭据**输入数据源凭据**对话框随即出现。 指定的用户名和密码以连接到 SAP 系统，然后单击**确定**。  
  
       如果你选择用于指定凭据的任何其他选项，则向导将继续到下一步。  
  
   5. 在中**设计查询**对话框框中，指定用于生成报表的查询字符串。 例如：  
  
      ```  
      SELECT TOP 2 KUNNR, NAME1 FROM KNA1 WHERE NAME1 LIKE @PARAM  
      ```  
  
       此查询将从 NAME1 其中是生成报表时将指定的名称 KNA1 表中检索前两个记录。  
  
       单击“下一步” 。  
  
   6. 在随后的对话框框中，您可以设计在其中你想要显示的报表的格式。 如果你想要使用的默认格式，请单击**完成 >>&#124;** 若要直接转到**完成**对话框。  
  
   7. 在中**完成向导**对话框中，指定报表的名称，查看摘要，，然后单击**完成**。 对于本主题中，指定作为报表的名称`SAPReport`。  
  
      现在可以查看报表。 有关如何查看报表的说明，请参阅[查看适用于 SAP 报告](../../adapters-and-accelerators/adapter-sap/view-the-reports-for-sap.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用包含 SSRS 的 SAP 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)