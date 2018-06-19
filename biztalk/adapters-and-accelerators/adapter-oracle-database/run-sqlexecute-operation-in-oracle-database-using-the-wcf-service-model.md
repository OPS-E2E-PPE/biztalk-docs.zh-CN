---
title: 使用 WCF 服务模型的 Oracle 数据库中运行 SQLEXECUTE 操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, performing a SQLEXECUTE operation
- SQLEXECUTE operation, performing a
- how to, invoke the SQLEXECUTE operation
ms.assetid: d3f61e5f-4453-4a76-9bc6-40d91cb58224
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6bda1c864e7a6eff442099d6caf1a2bba98e7f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215973"
---
# <a name="run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model"></a>使用 WCF 服务模型的 Oracle 数据库中运行 SQLEXECUTE 操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现一组标准的 Oracle 数据库项目上的操作。 通过使用这些操作，你可以执行诸如调用一个 Oracle 函数或过程中，或执行对表的基本 SQL 数据操作语言 (DML) 操作。 但是，可能会要求你执行操作的方案根据你的业务逻辑，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不能显示。 例如，你可能希望：  
  
-   执行上不显示的数据库项目的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; 例如，获取 CURVAL 或 NEXTVAL Oracle 序列。  
  
-   执行数据定义语言操作;例如，创建一个表。  
  
-   在未出现在设计时; 一个数据库项目上执行操作例如，更新中创建由业务逻辑的临时表的记录。  
  
-   执行对表比操作的更复杂 DML 操作的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]呈现; 例如，若要执行查询包括对 JOIN 子句。  
  
 对于这些类型的情况下，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]呈现 SQLEXECUTE 操作。 通过使用 SQLEXECUTE 操作，你可以对 Oracle 数据库执行参数化的 SQL 语句。 SQLEXECUTE 操作支持组成使你可以执行一次为每个集的相同 SQL 语句的参数集的输入的参数块。 SQLEXECUTE 操作返回泛型记录集内的 SQL 语句的结果。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 此主题使用 Oracle 序列中的示例名为 TID_SEQ。 使用 SDK 示例提供了一个脚本来生成此序列。 有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 WCF 服务模型生成专用的 WCF 客户端， **SQLEXECUTEClient**，SQLEXECUTE 操作。 下面的代码演示**SQLEXECUTEClient**以及调用以调用 SQLEXECUTE 操作的方法的签名。  
  
```  
public partial class SQLEXECUTEClient : System.ServiceModel.ClientBase<SQLEXECUTE>, SQLEXECUTE {  
  
    ...  
  
    public microsoft.lobservices.oracledb._2007._03.GenRecordRow[] SQLEXECUTE(string SQLSTATEMENT, string PARAMETERSCHEMA, microsoft.lobservices.oracledb._2007._03.PARAMETERDATA[] PARAMETERSET);   
}  
```  
  
 SQLEXECUTE 操作将返回泛型的记录集。 此记录集包含的值 （如果有） 返回的语句 SQLEXECUTE 操作执行。 你可以向 PARAMETERDATA 对象，其中每个包含表示为字符串的输入参数的集合的集合中的 SQLEXECUTE 操作传递输入参数的集。 下面的代码演示一 PARAMETERDATA 组的定义。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03 {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class PARAMETERDATA : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        ...  
  
        private string[] PARAMETERField;  
  
        ...  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public string[] PARAMETER {  
            get {  
                return this.PARAMETERField;  
            }  
            set {  
                this.PARAMETERField = value;  
            }  
        }  
    }  
}  
```  
  
## <a name="invoking-the-sqlexecute-operation"></a>调用 SQLEXECUTE 操作  
 若要使用 WCF 客户端调用 SQLEXECUTE 操作，请执行以下步骤。  
  
1.  生成**SQLEXECUTEClient**为目标表或视图的类。  
  
    > [!IMPORTANT]
    >  在根节点下显示 SQLEXECUTE 操作 (**/**) 中**选择类别**窗格中的**添加适配器服务引用**对话框。  
  
2.  创建的实例**SQLEXECUTEClient**类，并调用**SQLEXECUTE**方法对 Oracle 数据库执行 SQL 语句。  
  
 有关详细信息，有关如何创建一个 WCF 客户端类，在调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[与 Oracle 数据库适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)。  
  
 下面的示例使用**SQLEXECUTEClient**来获取通过执行以下 SQL 语句的 Oracle 序列，TID_SEQ，下一步值： `SELECT tid_seq.nextval id from DUAL`。 然后向控制台写入输出。  
  
```  
using (SQLEXECUTEClient sqlClient = new SQLEXECUTEClient("OracleDBBinding_SQLEXECUTE"))  
{  
    sqlClient.ClientCredentials.UserName.UserName = "SCOTT";  
    sqlClient.ClientCredentials.UserName.Password = "TIGER";  
    try  
    {  
        sqlClient.Open();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error opening SQL client " + ex.Message);  
        throw;  
    }  
    microsoft.lobservices.oracledb._2007._03.GenRecordRow[] sequenceRec =   
        new microsoft.lobservices.oracledb._2007._03.GenRecordRow[0];  
  
    try  
    {  
        sequenceRec = sqlClient.SQLEXECUTE("SELECT tid_seq.nextval id from DUAL", null, null);  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error executing SQL client " + ex.Message);  
        throw;  
    }  
  
    if (sequenceRec.Length > 0)  
    {  
        Console.WriteLine("TID_SEQUENCE value is {0}", sequenceRec[0].GenRecordColumn[0].ColumnValue);  
    }  
    else  
    {  
    Console.WriteLine("Couldn't get next TID_SEQUENCE value");  
    }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [开发使用 WCF 服务模型的 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)