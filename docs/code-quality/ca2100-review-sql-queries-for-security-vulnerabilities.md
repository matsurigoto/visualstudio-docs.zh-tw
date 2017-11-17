---
title: 'CA2100: Review SQL queries for security vulnerabilities | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Review SQL queries for security vulnerabilities
- ReviewSqlQueriesForSecurityVulnerabilities
- CA2100
helpviewer_keywords:
- CA2100
- ReviewSqlQueriesForSecurityVulnerabilities
ms.assetid: 79670604-c02a-448d-9c0e-7ea0120bc5fe
caps.latest.revision: 24
author: stevehoag
ms.author: shoag
manager: wpickett
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: 931e2dae6c7b773ca2b8236917146ab9410d3565
ms.contentlocale: zh-tw
ms.lasthandoff: 08/30/2017

---
# <a name="ca2100-review-sql-queries-for-security-vulnerabilities"></a>CA2100: Review SQL queries for security vulnerabilities
|||  
|-|-|  
|TypeName|ReviewSqlQueriesForSecurityVulnerabilities|  
|CheckId|CA2100|  
|Category|Microsoft.Security|  
|Breaking Change|Non-breaking|  
  
## <a name="cause"></a>Cause  
 A method sets the <xref:System.Data.IDbCommand.CommandText%2A?displayProperty=fullName> property by using a string that is built from a string argument to the method.  
  
## <a name="rule-description"></a>Rule Description  
 This rule assumes that the string argument contains user input. A SQL command string that is built from user input is vulnerable to SQL injection attacks. In a SQL injection attack, a malicious user supplies input that alters the design of a query in an attempt to damage or gain unauthorized access to the underlying database. Typical techniques include injection of a single quotation mark or apostrophe, which is the SQL literal string delimiter; two dashes, which signifies a SQL comment; and a semicolon, which indicates that a new command follows. If user input must be part of the query, use one of the following, listed in order of effectiveness, to reduce the risk of attack.  
  
-   Use a stored procedure.  
  
-   Use a parameterized command string.  
  
-   Validate the user input for both type and content before you build the command string.  
  
 The following [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] types implement the <xref:System.Data.IDbCommand.CommandText%2A> property or provide constructors that set the property by using a string argument.  
  
-   <xref:System.Data.Odbc.OdbcCommand?displayProperty=fullName> and <xref:System.Data.Odbc.OdbcDataAdapter?displayProperty=fullName>  
  
-   <xref:System.Data.OleDb.OleDbCommand?displayProperty=fullName> and <xref:System.Data.OleDb.OleDbDataAdapter?displayProperty=fullName>  
  
-   <xref:System.Data.OracleClient.OracleCommand?displayProperty=fullName> and <xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=fullName>  
  
-   [System.Data.SqlServerCe.SqlCeCommand](https://msdn.microsoft.com/library/system.data.sqlserverce.sqlcecommand.aspx) and  [System.Data.SqlServerCe.SqlCeDataAdapter](https://msdn.microsoft.com/library/system.data.sqlserverce.sqlcedataadapter.aspx)  
  
-   <xref:System.Data.SqlClient.SqlCommand?displayProperty=fullName> and <xref:System.Data.SqlClient.SqlDataAdapter?displayProperty=fullName>  
  
 Notice that this rule is violated when the ToString method of a type is used explicitly or implicitly to construct the query string. The following is an example.  
  
```  
int x = 10;  
string query = "SELECT TOP " + x.ToString() + " FROM Table";  
```  
  
 The rule is violated because a malicious user can override the ToString() method.  
  
 The rule also is violated when ToString is used implicitly.  
  
```  
int x = 10;  
string query = String.Format("SELECT TOP {0} FROM Table", x);  
```  
  
## <a name="how-to-fix-violations"></a>How to Fix Violations  
 To fix a violation of this rule, use a parameterized query.  
  
## <a name="when-to-suppress-warnings"></a>When to Suppress Warnings  
 It is safe to suppress a warning from this rule if the command text does not contain any user input.  
  
## <a name="example"></a>Example  
 The following example shows a method, `UnsafeQuery`, that violates the rule and a method, `SaferQuery`, that satisfies the rule by using a parameterized command string.  
  
 [!code-vb[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/VisualBasic/ca2100-review-sql-queries-for-security-vulnerabilities_1.vb)] [!code-csharp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CSharp/ca2100-review-sql-queries-for-security-vulnerabilities_1.cs)] [!code-cpp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CPP/ca2100-review-sql-queries-for-security-vulnerabilities_1.cpp)]  
  
## <a name="see-also"></a>See Also  
 [Security Overview](/dotnet/framework/data/adonet/security-overview)