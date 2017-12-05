---
title: "使用适用于 SAP 的数据提供程序来创建报表服务器项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fe985b5-ba67-4179-a31c-4f41106c32be
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9c7905fc7114feeca8b53589e1aa32a09495ca1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="use-the-data-provider-for-sap-to-create-a-report-server-project"></a>使用适用于 SAP 的数据提供程序来创建报表服务器项目
你必须创建报表服务器项目，使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，若要为 SAP 系统中可用的数据生成报表。 本主题将说明了如何创建报表服务器项目。  
  
## <a name="prerequisites"></a>先决条件  
 执行本主题中提供过程之前，请确保你安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]安装时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装。 有关详细信息[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，请参阅安装指南在\<*安装驱动器*\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。  
  
### <a name="to-create-a-report-server-project"></a>若要创建报表服务器项目  
  
1.  启动[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并创建一个报表服务器项目。 若要创建报表服务器项目，请执行以下操作：  
  
    1.  单击**文件**菜单上，单击**新建**，然后单击**项目**。  
  
    2.  在**新项目**对话框中，从**项目类型**列表中，选择**商业智能项目**。 从**Visual Studio 已安装的模板**列表中，选择**报表服务器项目**。  
  
    3.  指定的名称和位置的项目，然后单击**确定**。 对于本主题中，指定为项目的名称`SAP_ Report`。  
  
2.  添加新的数据源：  
  
    1.  在解决方案资源管理器，右键单击**共享数据源**，然后单击**添加新数据源**。  
  
    2.  在**共享数据源**对话框中，在**常规**选项卡上，指定数据源的名称。 有关本主题中，将名称指定为`SAPDataSource`。  
  
    3.  从**类型**列表中，选择**适用于 SAP 的数据提供程序**。  
  
    4.  在**连接字符串**框中，指定的连接字符串[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。 璝惠[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连接字符串，请参阅[SAP 连接字符串中读取有关数据提供程序类型](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。  
  
         ![创建数据源](../../adapters-and-accelerators/adapter-sap/media/8494c1a5-5e68-4178-a005-a6ea56d97ad7.gif "8494c1a5-5e68-4178-a005-a6ea56d97ad7")  
  
        > [!NOTE]
        >  你可以选择指定的凭据作为连接字符串的一部分，或者指定这些下一步中所述。  
  
    5.  在**凭据**选项卡上，选择下列情况之一，然后单击**确定**:  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**使用特定用户名和密码**|指定用户名和密码以连接到 SAP 系统。|  
        |**提示输入凭据**|生成报表时，应输入 SAP 系统的凭据。 **注意：**凭据指定为此选项将替代凭据，如果指定，作为连接字符串的一部分。|  
        |**无凭据**|如果你要作为连接字符串的一部分提供的用户名和密码，请选择此选项。|  
  
        > [!NOTE]
        >  报表服务器项目不支持 Windows 身份验证模式。  
  
3.  添加新报表：  
  
    1.  在解决方案资源管理器，右键单击**报表**，然后单击**添加新报表**。  
  
         这将启动报表向导。  
  
    2.  阅读欢迎屏幕上的信息，然后单击**下一步**。  
  
    3.  在**选择数据源**对话框框中，选择**共享数据源**选项中，选择**SAPDataSource**你在前一步骤中创建，然后单击**下一步**。  
  
    4.  如果你选择了**提示输入凭据**选项以创建数据源时指定的用户凭据**输入数据源凭据**对话框随即出现。 指定用户名和密码以连接到 SAP 系统，然后单击**确定**。  
  
         如果你选择用于指定凭据的任何其他选项，则向导将继续执行下一步。  
  
    5.  在**设计查询**对话框框中，指定用于生成报表的查询字符串。 例如：  
  
        ```  
        SELECT TOP 2 KUNNR, NAME1 FROM KNA1 WHERE NAME1 LIKE @PARAM  
        ```  
  
         此查询将从 NAME1 位置是将生成报表时指定的名称 KNA1 表中检索前两条记录。  
  
         单击 **“下一步”**。  
  
    6.  在后续的对话框中，你可以设计所需的报表显示在其中的格式。 如果你想要使用的默认格式，请单击**完成 >> &#124;**以直接转到**完成**对话框。  
  
    7.  在**完成向导**对话框中，指定报表的名称，查看摘要，，然后单击**完成**。 对于本主题中，指定为报表的名称`SAPReport`。  
  
     你现在可以查看报表。 有关如何查看报表的说明，请参阅[查看适用于 SAP 的报表](../../adapters-and-accelerators/adapter-sap/view-the-reports-for-sap.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用包含 SSRS 的 SAP 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)