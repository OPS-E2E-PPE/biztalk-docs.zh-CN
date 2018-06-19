---
title: 解决与适用于 SAP 的数据提供程序的问题 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, troubleshooting
- troubleshooting, Data Provider for SAP
ms.assetid: 6fe9baed-0404-4f15-b76e-88cc11c5ff46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba61b75f95fad429c70da42479f22a32fa4e5a65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217981"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-sap"></a>解决与适用于 SAP 的数据提供程序的问题
本部分讨论如何使用故障排除方法来解决操作使用时可能遇到的错误[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。  
  
##  <a name="BKMK_SAPUnknownParam"></a>使用 Data Provider for SAP 的未知的参数错误  
 **问题**  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]将报告以下错误：  
  
```  
Microsoft.Data.SAPClient.SAPException: Failed to retrieve data from SAP server --- > Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Unknown Parameter OUT_ZDATATABLE.  
```  
  
 **可能的原因**  
  
 自定义的 RFC、 Z_EXTRACT_DATA_OO，SAP 系统中安装的不是最新。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用自定义的 RFC，Z_EXTRACT_DATA_OO，执行对 SAP 表选择操作。  
  
 **解决方法**  
  
 你必须为可用的最新版本更新的自定义的 RFC。 此 RFC、 Z_EXTRACT_DATA_OO，都可以进行 adapterpacknoversion。 有关如何安装和卸载自定义的 RFC 的详细信息，请参阅[安装适用于 SAP 的数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。
  
##  <a name="BKMK_SAPOOM"></a>取消从 SAP 表中选择数据时的内存异常  
 **问题**  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]从 SAP 系统中选择数据时将引发内存不足异常。  
  
 **可能的原因**  
  
 默认情况下，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]一次检索 10,000 行。 此外，每个批行从 SAP 系统中检索存储在内存中。 因此，  
  
-   如果从中检索数据的表包含大量行，或  
  
-   如果表包含占用的内存，相当多的数据类型的列  
  
 内存使用情况[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]显著提高，并可能会导致内存不足异常。  
  
 **解决方法**  
  
 你可以更改最大从 SAP 系统中检索的行数。 你可以做到这一点与 SELECT 语句中指定了 batchsize 选项。 例如：  
  
```  
SELECT * FROM <tablename> OPTION 'batchsize 1000'  
```  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]现在一次检索仅 1000年行，因此不会不会占用大量的内存。  
  
##  <a name="BKMK_SAPQueryExcep"></a>执行查询采用带日期值的参数时出现异常  
 **问题**  
  
 执行一个查询使用采用日期值的参数的 EXECQUERY 命令时，则会得到以下异常：  
  
```  
ErrorCode=RFC_SYS_EXCEPTION. ErrorGroup=RFC_ERROR_SYSTEM_FAILURE.   
SapErrorMessage=Enter date in the format __.__.____.  
```  
  
 **可能的原因**  
  
 在执行查询使用 EXECQUERY 命令时，你始终必须采用 YYYYMMDD 格式指定日期值。  
  
 **解决方法**  
  
 请确保采用 YYYYMMDD 格式指定日期值。 例如：  
  
```  
EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1='20080606'  
```  
  
##  <a name="BKMK_SAPNOVARIANT"></a>执行查询使用 EXECQUERY 命令 NO_VARIANT 异常  
 **问题**  
  
 执行一个查询使用 EXECQUERY 命令时，则会得到以下异常：  
  
```  
Exception: Details: ErrorCode=RFC_EXCEPTION. ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage=NO_VARIANT.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: <RFC name>  
```  
  
 **可能的原因**  
  
 可以有两个可能的原因，此异常：  
  
1.  试图执行的查询具有在 SAP 系统中定义的变体。 变体，请参阅为已保存的一组可以执行的 SAP 查询时指定的选择条件。 例如，可以使用变体指定查询的默认值。  
  
2.  查询尝试执行都不具有 variant 类型的定义，也不期望将传递参数值。  
  
 **解决方法**  
  
1.  对于原因 1，请确保指定与查询关联的变量的名称。 例如：  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant =  ‘variant1’  
    ```  
  
2.  对于原因 2，请确保指定的查询命令时提供 dummy 参数名称和值。 例如，如果"myquery"查询不需要执行任何参数，EXECQUERY 命令必须指定为：  
  
    ```  
    EXECQUERY myquery @usergroup='mygroup',@P1 = 'dummy_value'  
    ```  
  
## <a name="see-also"></a>另请参阅  
[故障排除 SAP 适配器](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)