---
layout: post
title: "shoulda-matcher 요약"
date: 2014-03-31 16:31:12 +0900
comments: true
categories: 
---

one-liner 테스트

**ActiveModel Matcher**

matcher name | validation | summary(or validation's)
:-----------:|:-------:|-----------
allow_mass_assignment_of | | rails 3의 attr_accesible과 attr_protected macro 적용 유무
allow_value | validates_format_of | 특정 format을 만족하면 valid(ex. 정규표현식, 날짜타입)
ensure_inclusion_of | validates_inclusion_of | 포함하면 valid
ensure_exclusion_of | validates_exclusion_of | 포함하지 않아야 valid
ensure_lenghth_of | validates_length_of | 길이 관련 validation
have_secure_password | has_secure_password | bcrypt 암호화가 되었으면 valid
validate_absence_of | validates_absence_of | blank이면 valid
validate_acceptance_of | validates_acceptance_of | checkbox 같은 acceptance가 있으면 valid(ex. terms of service)
validate_confirmation_of | validates_confirmation_of | in-memory에 attribute를 생성하여 confirmation이 valid한지 체크
validate_numericality_of | validates_numericality_of | 숫자이면 valid
validate_presence_of | validates_presence_of | non blank이면 valid
validate_uniqueness_of | validates_uniqueness_of | unique하면 valid

</br></br>

**ActiveRecord Matchers**

matcher name | validation(or summary)
:-----------:|:-------
accept_nested_attributes_for | accepts_nested_attributes_for
belong_to | belongs_to
have_many | has_many, has_many :through
have_one | has_one, has_one :through
have_and_belong_to_many | has_and_belongs_to_many
have_db_column | 특정 column이 존재하는지 테스트
have_db_index | 특정 column의 index가 존재하는지 테스트
have_readonly_attribute | attr_readonly
serialize | serialize

</br></br>

**ActiveController Matchers**

matcher name | summary
:-----------:|:-------:|-----------
filter_param | 설정값 테스트(configuration)
permit | whitelist 파라미터 테스트
redirect_to | redirect 테스트
render_template | 특정 template을 렌더링하는지 테스트
render_with_layout | 특정 layout을 렌더링하는지 테스트
rescue_from | (확인중입니다.)
respond_with | 특정 status code와 함께 respond 되는지 테스트
route | 해당 controller, action, params를 생성하는지 테스트
set_session | session에 특정 hash 값이 존재하는지 테스트
set_the_flash | flash에 특정 hash 값이 존재하는지 테스트
use_after_filter / use_after_action | after_filter가 사용되는지 테스트
use_before_filter / use_before_action | before_filter가 사용되는지 테스트

</br></br>

**Independent Matchers**

non-Rails-dependent code test

</br>