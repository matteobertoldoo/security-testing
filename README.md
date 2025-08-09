# Tourism Management System - Security Analysis

A comprehensive security assessment of a Java-based web application for tourism management, identifying and exploiting vulnerabilities through static, dynamic, and manual testing approaches.

## 📋 Project Overview

This project presents a thorough security evaluation of the **Online Tourism Management System**, a web-based Java application designed for tour operating companies. The assessment was conducted as part of the Security Testing course 2024-2025 at the University of Trento.

## 🎯 Objectives

- Analyze and improve the security posture of a Java web application
- Identify common vulnerabilities in applications developed without security focus
- Apply comprehensive testing methodologies combining automated tools and manual analysis
- Document findings and provide actionable security recommendations

## 🏗️ Application Architecture

The tested application follows the **MVC (Model-View-Controller)** pattern:

- **Frontend**: JSPs, HTML, CSS, JavaScript
- **Backend**: Java Servlets handling business logic and database interactions
- **Database**: MySQL for data persistence
- **Functionality**: User management, package booking, hotel/transport reservations

## 🔧 Testing Methodology

### Static Analysis
- **Tool**: SpotBugs with Find-Sec-Bugs plugin
- **Focus**: Code-level vulnerability detection
- **Results**: 570 potential vulnerabilities identified

### Dynamic Analysis
- **Tool**: OWASP ZAP (Zed Attack Proxy)
- **Approach**: Runtime testing with active scanning
- **Results**: 1,289 alerts across different severity levels

### Manual Analysis
- **Method**: Code review and hands-on exploitation
- **Focus**: Context-aware vulnerability assessment
- **Results**: 6 critical vulnerabilities confirmed

## 🚨 Key Findings

### Critical Vulnerabilities Discovered

| Vulnerability Type | Count | Severity | Tool Detection |
|-------------------|--------|----------|----------------|
| SQL Injection | 48 | High | Static/Dynamic |
| Cross-Site Scripting (XSS) | 42 | High | All Methods |
| Broken Access Control | Multiple | High | Manual |
| CSRF | Multiple | Medium | Dynamic |
| Hardcoded Credentials | 1 | High | Manual |

### Security Issues Summary

- **Total Vulnerabilities**: 1,865 across all testing phases
- **True Positives**: Majority of flagged issues were exploitable
- **Average Exploitation Time**: ~10 minutes per vulnerability
- **Confidence Level**: 90% in manual findings, 80% in automated results

## 🛠️ Tools and Technologies

### Development Environment
- **IDE**: Eclipse
- **Database**: MySQL
- **Application Server**: Apache Tomcat

### Security Testing Tools
- **SpotBugs + Find-Sec-Bugs**: Static code analysis
- **OWASP ZAP v2.15**: Dynamic application security testing
- **Manual Testing**: Code review and exploitation validation

## 📊 Vulnerability Analysis

### High-Risk Issues
1. **SQL Time-Based Injection**: Database manipulation through response delays
2. **Stored XSS**: Persistent script injection in user inputs
3. **Authentication Bypass**: Direct URL access to admin functionalities
4. **Input Validation Failures**: Unvalidated parameters leading to multiple attack vectors

### Impact Assessment
- **Data Integrity**: Potential database manipulation and data theft
- **User Security**: Session hijacking and credential compromise
- **System Availability**: Possible service disruption through injection attacks

## 🔒 Security Recommendations

### Immediate Actions
1. **Implement Prepared Statements**: Replace direct SQL concatenation
2. **Input Sanitization**: Validate and encode all user inputs
3. **Access Control**: Enforce proper authentication and authorization
4. **CSRF Protection**: Implement anti-CSRF tokens for sensitive operations

### Long-term Improvements
- Adopt secure coding practices throughout development lifecycle
- Implement comprehensive security testing in CI/CD pipeline
- Regular security training for development team
- Deploy security-focused frameworks and libraries
