---
title: SAP 中 EXECQUERY 语句语法 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99bd7fbb-64f2-4327-a8ae-ccb574e56150
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5198335cfa1a7d2036ca05759edc7d04e28cc20b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="syntax-for-an-execquery-statement-in-sap"></a>SAP 中 EXECQUERY 语句语法
SAP GUI 可用于通过以图形方式中选择你想要查询，列和排序的顺序要包括在结果集等中的表创建查询。[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用户能够通过提供用户可用于执行查询在 SAP 系统中定义的 EXECQUERY 操作从 ADO.NET 应用程序执行此类查询。  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用自定义的 RFC Z_EXECUTE_SAP_QUERY SAP 系统中执行的预定义的查询。 自定义的 RFC 反过来执行 RSAQ_REMOTE_QUERY_CALL，这是 SAP 系统中定义的 RFC 标准。 因此，你可以使用 EXECQUERY 操作之前，必须在你将运行您的查询针对 SAP 系统中安装自定义的 RFC。 有关如何安装自定义的 RFC 的说明，请参阅[安装适用于 SAP 的数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。  
  
 本主题提供有关 EXECQUERY 操作中和其他与 EXECQUERY 操作相关的有用信息的语法的信息。  
  
## <a name="syntax-for-an-execquery-statement"></a>EXECQUERY 语句语法  
 以下部分介绍的使用针对 EXECQUERY 操作的语法规范[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  
  
```  
EXECQUERY <QueryName> @USERGROUP='usergroup' [, @WORKSPACE='X'] [, @VARIANT='variant']   
[, @P1='<value 1>’] [, @P2='<value 2>'] ... [, @Pn = '<value n>'] [, @P1!='<value 3>'] [, @P1 > '<value 4>'] [, @P1 <= '<value 2>']   
[, NOT @P1 = '<value 2>'] [, NOT @P1 != '<value 2>'] [, NOT @P1 > '<value 2>']   
[, @P1 BETWEEN '<value 1>' AND '<value 2>'] [, NOT @P1 BETWEEN '<value 1>' AND '<value2>’]  
[OPTION 'USEORIGINALCOLUMNNAMES']  
  
```  
  
 其中：  
  
-   **\<QueryName\>** 是 SAP 系统中定义的查询的名称。  
  
-   **USERGROUP**指在其中定义该查询的用户组。 这是必需的参数。  
  
-   **工作区**指在其中定义该查询的工作区。 在 SAP，有两个工作区-标准版和全局。 提供指定标准的工作区中的空白区域。 提供`X`指定全局工作区。 默认值为空的空间。  
  
-   **VARIANT**引用为已保存的一组可以执行的 SAP 查询时指定的选择条件。 例如，可以使用变体指定查询的默认值。  
  
-   **@Pn** n 是指<sup>th</sup> SAP 查询定义中的选择字段。  
  
-   **USEORIGINALCOLUMNNAMES**指定提供程序是否在数据集中，使用原始列名，因为它们存在于 SAP 系统。 默认情况下，提供程序使用 SAP 查询中定义的友好名称。 但是，如果在查询中的友好名称不是唯一的则 ADO.NET 客户端将从数据集读取数据时引发错误。 在这种情况下，你必须指定 USEORIGINALCOLUMNNAMES 选项，，该值指示提供程序在数据集中使用原始列名。  
  
    > [!IMPORTANT]
    >  你必须始终提供的值选项关键字在单引号中，例如，*USEORIGINALCOLUMNNAMES*。  
  
> [!NOTE]
>  有关如何将 SAP 查询的参数转换为 EXECQUERY 语法的信息，请参阅[转换 SAP 查询参数转换 EXECQUERY 命令](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)。  
  
### <a name="framing-an-execquery-syntax"></a>组帧 EXECQUERY 语法  
 组帧 EXECQUERY 操作来执行 SAP 查询的语法取决于如何在 SAP 系统中，包括在 SAP 中定义每个参数值定义该查询。 有关如何帧 EXECQUERY 语法来执行 SAP 查询的信息，请参阅[转换 SAP 查询参数转换 EXECQUERY 命令](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)。  
  
### <a name="additional-considerations-while-using-the-execquery-operation"></a>其他注意事项时使用 EXECQUERY 操作  
 本部分列出你必须使用与 EXECQUERY 语句时需要牢记的点[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  
  
-   指定用户组、 工作区中，和变体的值作为传递根据的是标准 SAP RFC RSAQ_REMOTE_QUERY_CALL。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不会验证指定为这些参数的值。  
  
-   EXECQUERY 操作返回的所有值都是字符串类型。  
  
-   查询名称、 用户组、 工作区中，和变体的关键字不区分大小写。 但是，参数名称必须始终是在上部 caseP 如@P1， @P2，等等。例如：  
  
    ```  
    EXECQUERY xyz USERGROUP=’mygrp’, NOT @P1= 'somevalue'  
    ```  
  
     与相同  
  
    ```  
    EXECQUERY xyz uSERgROUP=’mygrp’, NOT @P1= 'somevalue'  
    ```  
  
-   EXECQUERY 所支持的运算符是 >，<>、 =、 < =、 ！ =，，和 BETWEEN。  
  
-   EXECQUERY 操作不支持通配符。 例如，以下语句会提供预期的输出：  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
     但是，相同的查询执行带有通配符时将会出错。 请注意，使用通配符字符**@P2**。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = '*&*'  
    ```  
  
     在此示例中，你可能会收到一个错误，指出未找到任何数据。 这是因为查询搜索**\*&\***作为字符串，而不考虑星号 （*） 作为通配符。  
  
-   你始终必须采用 YYYYMMDD 格式指定日期值。  
  
-   如果执行具有 variant 类型在 SAP 系统中定义的查询，你可以作为命令的一部分指定变量的名称。 例如：  
  
    ```  
    EXECQUERY myquery @usergroup='mygroup',@variant = 'variant1'  
    ```  
  
    > [!NOTE]
    >  不需要指定变量的名称，如果在 SAP 系统中情况下，定义查询的默认变体。  
  
## <a name="see-also"></a>另请参阅  
 [使用 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)