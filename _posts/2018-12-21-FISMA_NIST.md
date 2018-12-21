---
layout: post
title: FISMA and NIST Notes
subtitle: Focus: Risk Management Framework
tags: [Blue Team, Compliance]
image: "/img/FISMA_NIST/Risk_Pyramid.png"
share-img: "/img/FISMA_NIST/Risk_Pyramid.png"
comments: true
---

## FISMA: Federal Information Security Management Act
	- Standards used by ALL federal agencies to categorize all information and information systems based on risk levels.
	- Guidelines recommending the types of information and information systems to be included in each category.
	- Minimum information security requirements (management, operational, and technical controls).
	- Defines three objectives: Confidentiality, Integrity, Availability.

## NIST Publications: 
	- ### FIPS: Federal Information Processing Standards: 
		- FISMA made FIPS mandatory for federal organizations
		- #### FIPS 199: Standards for Security Categorization. Defines three levels of impact if there should be a breach.
			- Potential impact is LOW if - The loss of CIA could be expected to have a LIMITED adverse effect on operations, assets, or individuals.
				- A system is LOW IMPACT if all three legs of the CIA triad are low.
			- Potential impact is MODERATE if - the loss of CIA could be expected to have a SERIOUS adverse effect on operations, assets, or individuals.
				- A system is MODERATE IMPACT if at least one leg of the CIA triad is moderate, and no leg is greater than moderate.
			- Potential impact is HIGH if - The loss of CIA could be expected to have a SEVERE OR CATASTROPHIC adverse effect on operations, assets, or individuals.
				- A system is HIGH IMPACT if at least one of the legs of the CIA triad are high.
		- #### FIPS 200: Minimum Security Requirements for Federal Information and Information Systems.
			- High Watermark: The highest degree of impact is the degree of which that system is categorized.
			- Defines 17 security-related areas (families) that: Represent a broad-based, balanced security program. These map to the areas that the RMF lists.
			<img src="/img/FISMA_NIST/Controls.png">
			- Includes Management, Operational, and Technical controls.
	- ### Special Publications: Provides guidance to federal organizations, and are not mandatory but may be mandated
		- #### SP 800-30 Rev 1: Guide for conducting risk assessments
			- Three Step Process for Risk Assessment:
				- Step 1: Prepare for the assessment
				- Step 2: Conduct the assessment
				- Step 3: Maintain the assessment
			- In the context of four risk factors:
				- Threats
				- Vulnerabilities
				- Likelihoods
				- Impacts
			- Threats X Vulnerabilities = Risk
			- Types of Assessments:
				- Qualitative Assessments:
					- Set of methods, principles, or rules for assessing risk based on non-numerical categories or levels.
					- Low, Moderate, High, Very High
				- Quantitative Assessments:
					- Assessing risk based on numbers. Where the meanings and proportionality of values are maintained inside and outside the context of the assessment.
				- Semi-Quantitative Assessments:
					- Set of methods, principles, or rules for assessing risk using bins (i.e. 0-15, 16-35, 35-70), using scales (i.e. 1-10) or representative numbers whose values and meanings are not maintained in other contexts.
		- #### SP 800-39: Managing Information Security Risk
			- Specifies a three-tiered approach of security risk:
				- Organization
				- Mission
				- Information System
			- Establish a relationship between aggregated risk from information systems and mission/business success.
			- Encourage senior leaders to recognize the importance of managing information security risk within the organization.
			- Help those with system level security responsibilities understand how system-level issues affect the organization/mission as a whole.
		- #### SP 800-53 Rev 4: Security controls catalog/assessment procedures
			- Multitiered Risk Management
				<img src="/img/FISMA_NIST/Risk_Pyramid.png">
				- Tier 1: Defining the mission/business processes needed to support the organizational missions/business functions. (Org as a whole).
				- Tier 2: Determining the security categories of the information systems needed to execute the mission/business processes. (Individual processes).
				- Tier 3: Incorporating information security requirements into the mission/business processes. (Systems).
			- Security Controls Structure
				- Controls are organized into 18 families (including the 17 families from FIPS 200), adding PM-Program Management.
			- Security Control Baselines
				- Minimum accepted security configuration based upon the security category and associated with the impact level of information systems determined in accordance with FIPS 199 and FIPS 200.
			- Security Control Designations
				- Three types of controls:
					- Common Controls:
						- Controls that may be inherited by one or more information systems. i.e an environmental control in a data center. The control isn't implemented explicitly on the system, but applies to the system.
				- System-Specific Controls:
						- Applied to a system.
				- Hybrid Controls:
					- When one part is common and another part is system-specific. 
			- External Service Providers
				- External service providers that have any interaction with federal systems must meet the same standards as the agencies.
		- #### SP 800-60: Guide for mapping types of information and information systems to security categories.
			- Describe how to establish a system security categorization based on the system's use, connectivity, and aggregate information content.
			- Suggest provisional security impact levels for common information types.
			- Discuss information attributes that may result in variances from the provisional impact level assignment.
			
