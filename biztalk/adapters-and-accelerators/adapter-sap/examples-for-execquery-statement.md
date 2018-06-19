---
title: EXECQUERY 语句中 BizTalk mySAP 适配器中的示例 |Microsoft 文档
description: EXECQUERY 示例和样本使用 BizTalk 适配器包 (BAP) 中的 mySAP 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4139af16-7c38-4ea2-b3e5-5acf8fc1f3c4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77c5d5877ff502b8fdca620d8b92e4427d3b73b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216237"
---
# <a name="examples-for-execquery-statement"></a>EXECQUERY 语句的示例
本主题提供示例 EXECQUERY 语句。  


## <a name="sample-statements"></a>示例语句
-   若要执行的查询采用 P1 和 P2 两个参数的命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
-   若要执行的查询采用参数 P1 的值的范围中的命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   若要执行的查询采用参数 P1 超出特定范围的值的命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   要执行的查询，可以执行参数 P1 的两个值之一的命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262', @P1 = '0000003263'  
    ```  
  
-   要执行不能采用参数的特定值的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 = '0000003262', NOT @P2 = '0000003263'  
    ```  
  
     在此示例中，P1 可以具有"0000003262"以外的任何值。 同样，P2 可以具有"0000003263"以外的任何值。  
  
-   要执行具有变体在 SAP 系统中定义的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant = ‘variant1’  
    ```  
  
     变体，请参阅为已保存的一组可以执行的 SAP 查询时指定的选择条件。 例如，可以使用变体指定查询的默认值。 对于具有针对所有参数定义的变量的查询，你不需要在命令文本中指定的参数。  
  
-   要执行不需要参数的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'some_dummy_value'  
    ```  
  
     对于不带参数的查询，你必须指定一个虚拟值参数。  
  
-   要执行包含需要日期值的参数的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '20080606'  
    ```  
  
     对于采用参数应为日期值的查询，你必须指定日期作为 YYYYMMDD。  
  
-   要通过指定参数的 null 值执行查询命令。  
  
     对于此类查询，不能指定形式的查询：  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'null'  
    ```  
  
     相反，如果你不希望指定一个值，你不应指定 P1 根本。  
  
-   要执行包含需要值大于一定数量的参数的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 > '0000003262'  
    ```  
  
-   要执行包含需要值的参数的查询命令早于一定数量。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 < '0000003262'  
    ```  
  
-   要执行包含需要值大于或等于一定数量的参数的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 >= '0000003262'  
    ```  
  
-   要执行包含预期值的较小或等于一定数量的参数的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 <= '0000003262'  
    ```  
  
-   要执行包含预期值不等于一定数量的参数的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 != '0000003262'  
    ```  
  