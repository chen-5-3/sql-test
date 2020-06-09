# sql-test


SELECT
            coupon.id,
            coupon.coupon_name,
            coupon.coupon_worth,
            coupon.coupon_type,
            coupon.purchase_way,
            coupon.coupon_grant_way,
            coupon.purchase_channel,
            coupon.coupon_overlay_rule,
            coupon.main_coupon_flag,
            coupon.max_acquirable_amount,
            coupon.discount,
            coupon.coupon_desc,
            coupon.use_rule_desc,
            coupon_batch.id AS couponBatchId,
            coupon_batch.main_coupon_batch_flag,
            coupon_batch.batch_name,
            coupon_batch.exchange_begin_time,
            coupon_batch.exchange_end_time,
            coupon_batch.charged_off_begin_time,
            coupon_batch.charged_off_end_time,
            coupon_batch.batch_total_amount,
            coupon_batch.granted_amount,
            coupon_batch.locked_amount,
            coupon_batch.audit_status
        FROM coupon
        INNER JOIN
            coupon_batch ON coupon.id = coupon_batch.coupon_id
        AND coupon_batch.delete_flag = 0
        AND coupon_batch.id = 1148
        AND coupon_batch.cancel_status = 0
        WHERE
            coupon.delete_flag = 0
        AND coupon.id = 1309
