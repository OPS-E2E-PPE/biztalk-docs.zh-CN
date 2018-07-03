---
title: 在 SAP 中的 EXECQUERY 语句的语法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99bd7fbb-64f2-4327-a8ae-ccb574e56150
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccf479438a5b0960a66b35ef7946df63d088284b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982014"
---
# <a name="syntax-for-an-execquery-statement-in-sap"></a>在 SAP 中的 EXECQUERY 语句的语法
可以使用 SAP GUI 以图形方式选择想要查询的列和排序的顺序您要包括在结果集，等等的表创建查询。[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用户能够通过提供用户可用于执行 SAP 系统中定义的查询的 EXECQUERY 操作从 ADO.NET 应用程序执行此类查询。  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用自定义的 RFC Z_EXECUTE_SAP_QUERY SAP 系统中执行预定义的查询。 自定义 RFC 依次执行 RSAQ_REMOTE_QUERY_CALL，这是在 SAP 系统中定义的 RFC 标准。 因此，您可以使用 EXECQUERY 操作之前，必须将运行针对查询 SAP 系统中安装自定义 RFC。 有关如何安装自定义 RFC 的说明，请参阅[安装适用于 SAP 数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。  
  
 本主题提供有关 EXECQUERY 操作和其他有用的信息与 EXECQUERY 操作相关的语法信息。  
  
## <a name="syntax-for-an-execquery-statement"></a>EXECQUERY 语句语法  
 以下部分介绍了使用 EXECQUERY 操作针对的语法规范[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  
  
```  
EXECQUERY <QueryName> @USERGROUP='usergroup' [, @WORKSPACE='X'] [, @VARIANT='variant']   
[, @P1='<value 1>’] [, @P2='<value 2>'] ... [, @Pn = '<value n>'] [, @P1!='<value 3>'] [, @P1 > '<value 4>'] [, @P1 <= '<value 2>']   
[, NOT @P1 = '<value 2>'] [, NOT @P1 != '<value 2>'] [, NOT @P1 > '<value 2>']   
[, @P1 BETWEEN '<value 1>' AND '<value 2>'] [, NOT @P1 BETWEEN '<value 1>' AND '<value2>’]  
[OPTION 'USEORIGINALCOLUMNNAMES']  
  
```  
  
 其中：  
  
- **\<QueryName\>** 是 SAP 系统中定义的查询的名称。  
  
- **用户组**指在其中定义查询的用户组。 这是必需的参数。  
  
- **工作区**指的是在其中定义查询的工作区。 在 SAP 中，有两个工作区-标准版和全局。 提供的空白空间，以指定的标准工作区。 提供`X`以指定的全局工作区。 默认值为空的空间。  
  
- **变体**是指可以执行 SAP 查询时指定的选择条件的已保存组。 例如，变体可用于指定查询的默认值。  
  
- <strong>@Pn</strong> n 是指<sup>th</sup> SAP 查询定义中的选择字段。  
  
- **USEORIGINALCOLUMNNAMES**指定提供程序是否使用原始列名称在数据集中，因为它们存在于 SAP 系统。 默认情况下，该提供程序使用 SAP 查询中定义的友好名称。 但是，如果在查询中的友好名称不唯一，则 ADO.NET 客户端将从数据集中读取数据时引发错误。 在这种情况下，必须指定 USEORIGINALCOLUMNNAMES 选项，指示提供程序在数据集中使用的原始列名称。  
  
  > [!IMPORTANT]
  >  您必须始终提供的值选项关键字在单引号中，例如，'*USEORIGINALCOLUMNNAMES*。  
  
> [!NOTE]
>  有关如何将 SAP 查询的参数转换为 EXECQUERY 语法的信息，请参阅[写入 EXECQUERY 命令转换 SAP 查询参数](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)。  
  
### <a name="framing-an-execquery-syntax"></a>组帧 EXECQUERY 语法  
 组帧 EXECQUERY 操作来执行 SAP 查询的语法取决于如何中 SAP 系统，包括在 SAP 中定义的每个参数值定义的查询。 说明如何明确 EXECQUERY 语法来执行 SAP 查询的信息，请参阅[写入 EXECQUERY 命令转换 SAP 查询参数](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)。  
  
### <a name="additional-considerations-while-using-the-execquery-operation"></a>其他注意事项虽然在使用 EXECQUERY 操作  
 本部分列出了使用 EXECQUERY 语句使用时必须牢记的点[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  
  
- 指定用户组、 工作区中，和变体的值以的方式传递的是标准 SAP RFC RSAQ_REMOTE_QUERY_CALL。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不会验证为这些参数指定的值。  
  
- EXECQUERY 操作返回的所有值都是字符串类型。  
  
- 查询名称、 用户组、 工作区中，和变体的关键字不区分大小写。 但是，参数名称必须始终是在上部 caseP 如@P1， @P2，等等。例如：  
  
  ```  
  EXECQUERY xyz USERGROUP=’mygrp’, NOT @P1= 'somevalue'  
  ```  
  
   与相同  
  
  ```  
  EXECQUERY xyz uSERgROUP=’mygrp’, NOT @P1= 'somevalue'  
  ```  
  
- EXECQUERY 所支持的运算符包括 >，<>、 =、 < =、 ！ =、 NOT、 BETWEEN 和。  
  
- EXECQUERY 操作不支持通配符字符。 例如，以下语句，为提供的预期的输出：  
  
  ```  
  EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
  ```  
  
   但是，相同的查询时使用的通配符字符执行时出现错误。 请注意，使用的通配符字符<strong>@P2</strong>。  
  
  ```  
  EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = '*&*'  
  ```  
  
   在此示例中，可能会收到一个错误，指出不找任何数据。 这是因为查询中搜索 **'\*&\*** 作为一个字符串，而不考虑星号 （*） 作为通配符。  
  
- 始终必须以 YYYYMMDD 格式表示指定日期值。  
  
- 如果执行具有 variant 类型的 SAP 系统中定义的查询，您可以指定变量名作为命令的一部分。 例如：  
  
  ```  
  EXECQUERY myquery @usergroup='mygroup',@variant = 'variant1'  
  ```  
  
  > [!NOTE]
  >  不需要指定变量的名称，如果默认变体在 SAP 系统中定义的查询。  
  
## <a name="see-also"></a>请参阅  
 [使用 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)