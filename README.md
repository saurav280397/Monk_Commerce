monk-commerce-coupon-api/
├── .gitignore
├── pom.xml                                   <-- Maven configuration (dependencies, build)
├── README.md                                 <-- Project documentation, use cases, and limitations
│
└── src/
    ├── main/
    │   ├── java/
    │   │   └── com/monkcommerce/couponapi/    <-- Root package
    │   │       ├── CouponApiApplication.java   <-- Application entry point
    │   │       │
    │   │       ├── controller/               <-- REST API Endpoints (GET, POST /coupons)
    │   │       │   └── CouponController.java
    │   │       │
    │   │       ├── model/                    <-- JPA Entities (Database structure)
    │   │       │   └── Coupon.java             <-- The main Coupon entity
    │   │       │
    │   │       ├── repository/               <-- Data Access Layer (Spring Data JPA)
    │   │       │   └── CouponRepository.java
    │   │       │
    │   │       ├── service/                  <-- Business Logic Orchestration
    │   │       │   ├── CouponService.java      <-- Handles CRUD, filtering, and calling strategies
    │   │       │   └── discount/             <-- Discount Logic (STRATEGY PATTERN - for extensibility)
    │   │       │       ├── DiscountStrategy.java
    │   │       │       ├── CartWiseDiscountStrategy.java
    │   │       │       ├── ProductWiseDiscountStrategy.java
    │   │       │       └── BxGyDiscountStrategy.java
    │   │       │
    │   │       ├── dto/                      <-- Data Transfer Objects (Request/Response)
    │   │       │   ├── Cart.java
    │   │       │   ├── CartItem.java
    │   │       │   └── ApplicableCouponDTO.java
    │   │       │
    │   │       └── exception/                <-- Custom Exception Handling
    │   │           └── ResourceNotFoundException.java
    │   │
    │   └── resources/
    │       ├── application.properties          <-- Server port, H2 configuration
    │       └── data.sql                        <-- Optional: SQL for initial coupon seeding
    │
    └── test/
        └── java/
            └── com/monkcommerce/couponapi/
                └── service/
                    └── discount/
                        └── CartWiseDiscountStrategyTest.java <
