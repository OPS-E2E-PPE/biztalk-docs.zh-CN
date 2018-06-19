---
title: 对于 SAP 数据提供程序安装自定义的 Rfc |Microsoft 文档
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
ms.openlocfilehash: 0aff501e5bf59d6ae22d9ad2a00e0e5ff5ad4605
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25966708"
---
# <a name="install-custom-rfcs-for-the-data-provider-for-sap"></a>对于 SAP 数据提供程序安装自定义的 Rfc
如果你想要使用用于 mySAP Business Suite.NET Framework 数据提供程序访问 SAP 系统，请安装自定义的 Rfc。

[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要自定义的 Rfc 执行某些 SAP 系统上的操作：
  
-   运行选择的操作，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要 Z_EXTRACT_DATA_OO RFC。  
  
-   运行 EXECQUERY 操作[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要 Z_EXECUTE_SAP_QUERY RFC。  
  
若要执行这些 SAP 系统上的操作，必须在 SAP 系统上安装这些自定义的 Rfc。 如果你选择安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连同[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，安装程序将复制的 RFC 传输[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]为压缩文件 (customRFC.zip) 系统上安装适配器。 Zip 文件通常安装在*\<安装驱动器\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft.NET Framework 数据提供程序为 mySAP Business Suite*。 
  
 提取 zip 文件之后, 你将找到四个数据文件、 两个以下命名模式 K9 *。BI1 （例如，类似于 K900534。BI1)，和其他两个以下模式 R9\*。BI1 （例如，类似于 R900534。BI1)。  
  

  
1.  将提取的文件复制到 SAP 应用程序服务器运行适配器的计算机。  
  
    1.  SAP 应用程序服务器的开发系统 SAP / 3 系统管理员身份登录。  
  
    2.  将具有以下命名模式： K9 * 两个传输文件的复制。从适配器到以下目录 server 上运行的 SAP 应用程序的计算机上的安装目录的 BI1:  
  
         `<drive>:\usr\sap\trans\cofiles`  
  
    3.  将具有以下命名模式： R9 * 两个传输文件的复制。从适配器到以下目录 server 上运行的 SAP 应用程序的计算机上的安装目录的 BI1:  
  
         `<drive>:\usr\sap\trans\data`  
  
2.  加载到 SAP 应用程序服务器上的传输缓冲区的传输。  
  
    1.  在命令提示符处，导航到 SAP 应用程序服务器上的传输程序目录：  
  
         `<drive>:\usr\sap\trans\bin`  
  
    2.  若要载入的传输缓冲区的传输，请执行下面的命令`\usr\sap\trans\bin`目录和替换*sysid*与开发系统的系统 ID:  
  
        ```  
        tp addtobuffer <TransportNumber> <sysid> pf=TP_DOMAIN_<sysid>.PFL  
        ```  
  
         其中， *TransportNumber*是实际传输数 (例如 BI1K900534)。  
  
    3.  后`tp`命令运行完以后，你将看到类似于以下报表：  
  
        ```  
        This is tp version 320.56.66 (release 620)  
        Addtobuffer successful for TransportNumber  
        tp finished with return code: 0  
        ```  
  
         返回代码"0"意味着该操作成功。  
  
         返回代码为 0 或 4 是可接受的。 如果你收到返回代码的 8 或更高版本，请与 Microsoft 客户服务和支持联系。  
  
        > [!IMPORTANT]
        >  第二个系列传输文件，请重复步骤 (b) 和 (c)。  
  
        > [!NOTE]
        >  你可以轻松地实际传输数派生 cofile 文件名称。 例如，名为 K900534 cofile。BI1 提供传输大量 BI1K900534。  
  
3.  导入 SAP 传输。  
  
    1.  执行以下命令在命令提示符：  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL  
        ```  
  
         替换*sysid*与开发系统的系统 ID。 替换*clientnumber*具有客户端数量的开发系统。  
  
         U2 参数可用于覆盖以前安装的对象，如下所示：  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> U2  
        ```  
  
         或  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL U2  
        ```  
  
        > [!NOTE]
        >  你可以轻松地实际传输数派生 cofile 文件名称。 例如，名为 K900534 cofile。BI1 提供传输大量 BI1K900534。  
  
    2.  后`tp`命令运行完以后，你将看到类似于以下报表：  
  
        ```  
        This is tp version 320.56.66 (release 620)  
        This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
        R3trans.exe finished (0000).  
        This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
        R3trans.exe finished (0000).  
        tp finished with return code: 0  
        ```  
  
         返回代码"0"意味着该操作成功。  
  
         返回代码为 0 或 4 是可接受的。 如果你收到返回代码的 8 或更高版本，请与 Microsoft 客户服务和支持联系。  
  
        > [!IMPORTANT]
        >  传输文件的第二个集，请重复步骤 （a） 和 (b)。  
  
4.  检查传输日志。  
  
5.  检查在 SAP GUI 传输管理器中使用事务 SE09 以验证没有错误传输日志。  
  
 设置用户授权  
 Z_EXTRACT_DATA_OO RFC 需要具有特定的授权对象的用户 Id。 使用 SAP GUI 授权管理工具在 RFC 执行设置的最小限制：  
  
> [!NOTE]
>  不需要设置 Z_EXECUTE_SAP_QUERY RFC 的授权。  
  
-   Z_EXTRACT_DATA_OO 需要 S_TABU_DIS 和 Z_EIP_TABL。 以下值提供 S_TABU_DIS，允许用户在系统中查看任何表的元数据的最小限制。  
  
    -   ACTVT: 03  
  
    -   DICBERCLS: *  
  
     DICBERCLS 可用于通过授权类限制对表的授权。  
  
     TDDAT 表可用于查看表的授权类。  
  
    > [!NOTE]
    >  以防止表维护事务更改到表，你应仅授予在生产环境中的显示特权 (ACTVT: 03 设置允许的活动来显示)。  
  
     Z_EIP_TABL 的最小值是：  
  
    -   ACTVT: 03  
  
    -   表: *  
  
     可以使用表来显式定义授权的表。 还请注意，S_TABU_DIS 还可在其他事务中。  
  
##### <a name="to-set-user-authorization"></a>若要设置用户授权  
  
1.  启动 SAP GUI。 转到 T 代码，类型`pfcg`，然后按 ENTER。  
  
2.  在**角色**文本框中，输入你想要创建，例如，角色名称`ZTEST`，然后单击**角色**。  
  
3.  在**创建角色**页上，单击**授权**选项卡。  
  
     如果系统提示您保存该角色，请单击**是**。  
  
4.  在**更改角色**页上，单击**更改授权数据**按钮。  
  
5.  如果系统提示你选择的模板**选择模板**对话框中，单击**不选择模板**。  
  
6.  在**更改角色： 授权**页上，单击**手动**按钮。  
  
7.  在**手动选择的授权**框中，输入授权对象的名称`Z_EIP_TABL`，然后按 enter 键。  
  
8.  在**更改角色： 授权**页上，展开节点，直到你看到的文本框中**活动**和**表名**。 有关**活动**文本框中，输入值`03`。 有关**表名**文本框中，输入值`*`。  
  
9. 单击**保存**按钮以生成配置文件。  
  
10. 返回到**更改角色**页上，单击**用户**选项卡。  
  
11. 在**用户**选项卡上，通过输入中的用户名称将分配角色的用户 ID**用户 ID**列并单击**用户比较**按钮。  
  
12. 在**比较角色用户的主记录**，单击**完成比较**更新的主记录。 当系统提示保存角色，单击**是**。  
  
13. 保存并退出。  
  
验证自定义的 RFC 安装  
 安装自定义的 Rfc 之后，你可以验证是否正确安装了 Rfc。  
  
-   对于 Z_EXECUTE_SAP_QUERY RFC，您可以执行，通过执行中 SAP 系统使用的预定义的查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  
  
-   对于 Z_EXTRACT_DATA_OO RFC，您可以执行，通过执行以下测试，确认 RFC 运行，并在你的系统中可供使用。  
  
##### <a name="to-test-the-installation-of-zextractdataoo"></a>若要测试的 Z_EXTRACT_DATA_OO 安装  
  
1.  在 SAP GUI 授权管理工具中，执行 SE37，函数模块 Z_EXTRACT_DATA_OO，，然后在测试模式下运行 RFC，通过按`F8`。 如下所示填充参数。  
  
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
  
2.  单击**执行**或按`F8`。  
  
3.  在结果窗格中，检查以下内容。  
  
    |||  
    |-|-|  
    |OUT_TABLEHEADER|\<T000 常规元数据\>|  
    |OUT_TECHNICALSETTINGS|\<T000 技术数据库级别的元数据\>|  
    |OUT_RECORDLENGTH|\<取决于 SAP 版本\>|  
    |OUT_RECORDCOUNT|\<与上 T000 SE16 系统中确认客户端的数量\>|  
    |OUT_ZDATATABLE|\<确认此结果与源数据在 T000 上使用 SE 16\>|  
    |OUT_RETURN_TAB|S 001 Success|  
  
## <a name="remove-the-rfc-for-the-data-provider-for-sap"></a>对于 SAP 数据提供程序删除 RFC  
  
1.  在 SAP GUI 对象导航 (SE80)，查找与 ZMSBI 开发类的所有对象。  
  
2.  在以下的字典对象文件夹中删除与 ZMSBI 开发类的所有对象：  
  
    -   结构  
  
    -   函数组  
  
    -   授权的对象  
  
3.  引发一个传输，并将它迁移通过 RFC （开发、 测试和生产系统，例如） 的安装位置的每个系统。  
  
     以获取进一步的帮助，请与您的 SAP 基础管理员联系。  
     
## <a name="next"></a>Next
[了解用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)  
[SAP 适配器教程](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)