---
title: 安装适用于 SAP 的数据提供程序的自定义 Rfc |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installation, custom RFCs for the Data Provider for SAP
- installing, custom RFCs for the Data Provider for SAP
- installing custom RFCs, how to
ms.assetid: 7a99db70-fa5a-4c04-9dc7-b71613d4364e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f94bb4b6a6f094211654f5c3c0964bbf84d42f56
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989590"
---
# <a name="install-custom-rfcs-for-the-data-provider-for-sap"></a>安装适用于 SAP 的数据提供程序的自定义 Rfc
如果你想要使用用于 mySAP Business Suite 的.NET Framework 数据提供程序来访问 SAP 系统，安装自定义 Rfc。

[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要执行某些操作到 SAP 系统上的自定义 Rfc:
  
- 运行选择的操作，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要 Z_EXTRACT_DATA_OO RFC。  
  
- 运行 EXECQUERY 操作[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要 Z_EXECUTE_SAP_QUERY RFC。  
  
若要执行这些操作上的 SAP 系统，必须在 SAP 系统上安装这些自定义 Rfc。 如果您选择安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连同[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，安装程序将复制的 RFC 传输[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]为压缩文件 (customRFC.zip) 系统上安装适配器。 Zip 文件通常安装在*\<安装驱动器\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft.NET Framework 数据提供程序用于 mySAP Business Suite*。 
  
 提取 zip 文件后, 您将找到四个数据文件、 两个以下命名模式 K9 *。BI1 （例如，类似于 K900534。BI1)，和其他两种模式 R9\*。BI1 （例如，类似于 R900534。BI1)。  
  

  
1. 将提取的文件复制到 SAP 应用程序服务器运行适配器的计算机。  
  
   1.  以 SAP R/3 系统管理员，以在开发系统的 SAP 应用程序服务器登录。  
  
   2.  复制使用的命名模式 K9 * 的两个传输文件。从 SAP 应用程序服务器上的以下目录中运行适配器的计算机上安装目录 BI1:  
  
        `<drive>:\usr\sap\trans\cofiles`  
  
   3.  复制使用的命名模式 R9 * 的两个传输文件。从 SAP 应用程序服务器上的以下目录中运行适配器的计算机上安装目录 BI1:  
  
        `<drive>:\usr\sap\trans\data`  
  
2. 加载到 SAP 应用程序服务器上的传输缓冲区的传输。  
  
   1.  在命令提示符处，导航到 SAP 应用程序服务器上的传输程序目录：  
  
        `<drive>:\usr\sap\trans\bin`  
  
   2.  若要加载到传输缓冲区的传输，执行以下命令，`\usr\sap\trans\bin`目录并替换*sysid*与在开发系统的系统 ID:  
  
       ```  
       tp addtobuffer <TransportNumber> <sysid> pf=TP_DOMAIN_<sysid>.PFL  
       ```  
  
        其中， *TransportNumber*是实际传输数字 (例如 BI1K900534)。  
  
   3.  之后`tp`命令完成，你将看到类似于以下报表：  
  
       ```  
       This is tp version 320.56.66 (release 620)  
       Addtobuffer successful for TransportNumber  
       tp finished with return code: 0  
       ```  
  
        返回代码"0"表示操作成功。  
  
        返回代码为 0 或 4 是可接受的。 如果收到返回代码为 8 或更高版本，请与 Microsoft 客户服务和支持联系。  
  
       > [!IMPORTANT]
       >  传输文件的第二个集，请重复步骤 (b) 和 (c)。  
  
       > [!NOTE]
       >  您可以轻松地实际传输数派生 cofile 文件名称。 例如，名为 K900534 cofile。BI1 提供 BI1K900534 传输数。  
  
3. 导入 SAP 传输。  
  
   1.  执行以下命令在命令提示符：  
  
       ```  
       tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL  
       ```  
  
        替换*sysid*与在开发系统的系统 ID。 替换*clientnumber*开发系统的客户端数。  
  
        U2 参数可用于覆盖以前安装的对象，如下所示：  
  
       ```  
       tp import <TransportNumber> <sysid> client=<clientnumber> U2  
       ```  
  
        或多个  
  
       ```  
       tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL U2  
       ```  
  
       > [!NOTE]
       >  您可以轻松地实际传输数派生 cofile 文件名称。 例如，名为 K900534 cofile。BI1 提供 BI1K900534 传输数。  
  
   2.  之后`tp`命令完成，你将看到类似于以下报表：  
  
       ```  
       This is tp version 320.56.66 (release 620)  
       This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
       R3trans.exe finished (0000).  
       This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
       R3trans.exe finished (0000).  
       tp finished with return code: 0  
       ```  
  
        返回代码"0"表示操作成功。  
  
        返回代码为 0 或 4 是可接受的。 如果收到返回代码为 8 或更高版本，请与 Microsoft 客户服务和支持联系。  
  
       > [!IMPORTANT]
       >  传输文件的第二个集，请重复步骤 （a） 和 (b)。  
  
4. 检查传输日志。  
  
5. 请查看在 SAP GUI 传输管理器中使用事务 SE09 以验证没有错误传输日志。  
  
   设置用户授权  
   Z_EXTRACT_DATA_OO RFC 要求使用特定的授权对象的用户 Id。 使用 SAP GUI 授权管理工具的 RFC 执行设置的最小限制：  
  
> [!NOTE]
>  不需要设置 Z_EXECUTE_SAP_QUERY RFC 的授权。  
  
- Z_EXTRACT_DATA_OO 需要 S_TABU_DIS 和 Z_EIP_TABL。 以下值提供 S_TABU_DIS，允许用户查看系统中的任何表的元数据的最小限制。  
  
  - ACTVT: 03  
  
  - DICBERCLS: *  
  
    DICBERCLS 可用于通过授权类来限制对表的授权。  
  
    TDDAT 表可用于查看表的授权类。  
  
  > [!NOTE]
  >  若要通过表维护事务将防止对表的更改，应仅授予在生产环境中的显示特权 (ACTVT: 03 设置允许的活动来显示)。  
  
   Z_EIP_TABL 的最小值是：  
  
  - ACTVT: 03  
  
  - 表: *  
  
    可以使用表来显式定义经过授权的表。 同时请注意，S_TABU_DIS 还可在其他事务中。  
  
##### <a name="to-set-user-authorization"></a>若要设置用户授权  
  
1.  启动将 SAP GUI。 转到 T 代码，类型`pfcg`，然后按 ENTER。  
  
2.  在中**角色**文字框中，输入你想要创建，例如，一个角色名称`ZTEST`，然后单击**角色**。  
  
3.  在中**Create Role**页上，单击**授权**选项卡。  
  
     如果系统提示您保存角色，请单击**是**。  
  
4.  在中**更改角色**页上，单击**更改授权数据**按钮。  
  
5.  如果系统提示你选择从模板**选择模板**对话框中，单击**不选择模板**。  
  
6.  在中**更改角色： 授权**页上，单击**手动**按钮。  
  
7.  在中**手动选择的授权**框中，输入授权对象的名称`Z_EIP_TABL`然后按 ENTER。  
  
8.  在中**更改角色： 授权**页上，展开节点，直到您看到的文本框**活动**并**表名**。 有关**活动**文字框中，输入值`03`。 有关**表名称**文字框中，输入值`*`。  
  
9. 单击**保存**按钮以生成该配置文件。  
  
10. 返回到**更改角色**页上，单击**用户**选项卡。  
  
11. 在中**用户**选项卡上，通过输入中的用户名称将分配角色的用户 ID**用户 ID**列，然后单击**用户比较**按钮。  
  
12. 在中**比较角色用户主记录**，单击**完成比较**更新主记录。 当系统提示保存角色，请单击**是**。  
  
13. 保存并退出。  
  
验证自定义 RFC 的安装  
 安装自定义 Rfc 后，可以验证是否已正确安装 Rfc。  
  
- Z_EXECUTE_SAP_QUERY rfc，就可以做到在 SAP 系统中使用执行预定义的查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  
  
- 对于 Z_EXTRACT_DATA_OO RFC，可以执行，通过执行以下测试，以确认，RFC 运行，并且可随时用于在系统中。  
  
##### <a name="to-test-the-installation-of-zextractdataoo"></a>若要测试的 Z_EXTRACT_DATA_OO 安装  
  
1.  SAP GUI 授权管理工具中执行 SE37，函数模块 Z_EXTRACT_DATA_OO，，然后在测试模式下运行 RFC，通过按`F8`。 按如下所示填充参数。  
  
    |||  
    |-|-|  
    |IN_METADATA_ONLY||  
    |IN_METADATA_LANGUAGE|EN|  
    |IN_FROM_TABLE|T000|  
    |IN_OUTPUT_MODE|S|  
    |IN_OUTPUT_FILENAME||  
    |IN_USE_FIELD_EXITS|X|  
    |IN_SET_ROWCOUNT|0|  
    |IN_DELIMITER||  
    |IN_PACKET_SIZE|50,000|  
    |IN_MAX_WRITE_ATTEMPTS|4|  
    |IN_RETRY_DELAY|30|  
    |IN_SQL_DATES_ON||  
  
2.  单击**Execute**或按`F8`。  
  
3.  在结果窗格中，检查以下内容。  
  
    |||  
    |-|-|  
    |OUT_TABLEHEADER|\<T000 常规元数据\>|  
    |OUT_TECHNICALSETTINGS|\<T000 技术的数据库级别元数据\>|  
    |OUT_RECORDLENGTH|\<取决于 SAP 版本\>|  
    |OUT_RECORDCOUNT|\<确认在 T000 SE16 与系统中的客户端数\>|  
    |OUT_ZDATATABLE|\<确认此结果与使用 SE 16 上 T000 的源数据\>|  
    |OUT_RETURN_TAB|S 001 成功|  
  
## <a name="remove-the-rfc-for-the-data-provider-for-sap"></a>删除数据提供程序适用于 SAP RFC  
  
1.  在 SAP GUI 对象导航 (SE80)，查找与 ZMSBI 开发类的所有对象。  
  
2.  在以下的字典对象文件夹中删除具有 ZMSBI 开发类的所有对象：  
  
    -   结构  
  
    -   函数组  
  
    -   已授权的对象  
  
3.  引发一个传输，并将其迁移通过 RFC （开发、 测试和生产系统，例如） 安装每个系统。  
  
     进一步的帮助，请联系您的 SAP 基础管理员。  
     
## <a name="next"></a>Next
[了解用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)  
[SAP 适配器教程](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)