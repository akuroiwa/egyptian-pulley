===========================================
The Pulley System with Pillars and Sandbags
===========================================
A Feasible Solution for the Construction of the Great Pyramids
--------------------------------------------------------------

:authors:
   Akihiro Kuroiwa,
   ChatGPT of OpenAI
:date: 2023/04/21

Pulley
======

The Great Pyramid of Giza is a testament to the ingenuity and wisdom of the ancient Egyptians. However, the method by which they constructed this enormous structure remains a mystery. While there are various theories, I propose the use of a pulley system employing pillars and sandbags.

An excavation by the team from the University of Liverpool uncovered a ramp system that used stakes [#]_. In my opinion, I believe that the stakes and ropes were not used merely as simple pulleys but as a compound pulley system. As you know, a compound pulley consists of a fixed pulley and a moving pulley and is currently used in modern elevators and cranes.

#. Drive stakes on both sides of the ramp to act as pillars.
#. Secure a rope to the pillars to serve as a starting point.
#. In front of the sled carrying the massive stones, attach a stone beam with multiple grooves that function as pulleys.
#. Pass a rope from the starting pillar on the right side through the sled's pulley and then pass the rope through the farthest pillar on the right side.
#. Repeat step 4 above four times between the right pillar and the sled's pulley.
#. Repeat step 5 on the left side using four pillars.
#. Finally, tie the end of the rope to a cart.
#. Load the cart with sandbags to act as weights and pull the rope by hand on flat ground.

Thus, eight pillars, excluding the starting point pillar, would function as fixed pulleys, with each rope passing through the moving pulleys attached to the sled. Even without a compound pulley, it is possible to create multiple moving pulleys using this method. If there were four support pillars on each side of the ramp, two moving pulleys could be created.

This pulley system may have also been used inside the pyramid's grand gallery. While stakes were used as pillars during transportation from the quarry, it is believed that beams were used in place of stakes inside the grand gallery.

The advantage of this method is that beams used as fixed pulleys in a compound pulley system can distribute the weight borne by each beam, allowing the load to be carried more efficiently.

Using beams and sandbags in a pulley system and constructing a grand gallery are the most plausible explanations for how the ancient Egyptians built the Great Pyramid. With this method, they could have transported enormous stones without the use of cranes or modern machinery.

Compared to the internal ramp theory proposed by Monsieur Jean-Pierre Houdin, the pulley system using beams and sandbags is a more straightforward and easily understandable solution. However, this proposal is only a partial modification and does not completely negate Monsieur Houdin's theory.

Sandbags were not only used as weights for the pulleys, but also as the outer frame of the inclined plane that was likely constructed during the pyramid's construction.

This inclined plane would have been used to transport heavy building materials up to higher levels of the pyramid. The sandbags would have been stacked in a zigzag pattern to create the slope of the ramp, and then covered with a layer of mortar or plaster to create a smooth surface for the workers and materials to move on.

Earthbags [#]_ have also been used in modern times as a sustainable and low-cost building material. They are essentially sacks filled with a mixture of soil, sand, and cement, which are then stacked and compacted to create walls. The resulting structure is incredibly durable, resistant to natural disasters like earthquakes and hurricanes, and energy-efficient due to its thick walls.

Overall, the use of sandbags in the construction of the pyramids is just one example of the ingenious building techniques that were developed by ancient civilizations. These techniques continue to inspire and inform modern sustainable building practices, and remind us of the incredible engineering feats that were accomplished by our ancestors.



Calculation
===========

Calculate the tensile force on the plane and on the slope when the compound pulley is used [#]_.

.. code-block:: python

   import math

   def calc_force_planar(friction, weight):
       return friction * weight

   def calc_force_slope(weight, angle, friction):
       angle_radian = angle * math.pi / 180
       return weight * math.sin(angle_radian) + weight * friction * math.cos(angle_radian)

   def calc_compound_pulleys(num_pillars, efficiency, weight):
       num = (num_pillars - 1) * 2
       return weight / (num * (efficiency / 100)**num)

   # example usage
   weight = 2500 # kg
   efficiency = 98 # %
   angle = 26.3123 # degree
   friction = 0.8
   num_pillars = 13 # number of pillars
   force_planar = calc_force_planar(friction, weight)
   force_slope = calc_force_slope(weight, angle, friction)
   force_compound_pulleys_planar = calc_compound_pulleys(num_pillars, efficiency, force_planar)
   force_compound_pulleys_slope = calc_compound_pulleys(num_pillars, efficiency, force_slope)

   print("Planar force: {:.2f} kgf".format(force_planar))
   print("Slope force: {:.2f} kgf".format(force_slope))
   print("Compound pulleys planar force: {:.2f} kgf".format(force_compound_pulleys_planar))
   print("Compound pulleys slope force: {:.2f} kgf".format(force_compound_pulleys_slope))

::

   Planar force: 2000.00 kgf
   Slope force: 2900.94 kgf
   Compound pulleys planar force: 135.33 kgf
   Compound pulleys slope force: 196.29 kgf



Tomb of King Khufu
==================

As Mr. Sakuji Yoshimura has pointed out, I don't think pyramids are actually tombs.
The Pyramids of Giza, like obelisks, should be regarded as mere parts of temples or funerary complexes, while the tombs of the pharaohs are believed to be located underground.
If the custom was also followed in later generations, then we should assume that a mastaba for King Khufu was dug on the west side of the pyramid, since Hatshepsut's mortuary temple is located on the east side of the Valley of the Kings.

The fact that the Sphinx of Giza faces east also confirms this. The Karnak Temple and the Luxor Temple are connected by the Avenue of Sphinxes, and if this is also inherited from the custom, it can be imagined that there are not only one sphinx but also multiple sphinxes at Giza.



Reference
=========

.. [#] `University of Liverpool. (2018).
   Ancient quarry ramp system may have helped workers build Egypt’s Great Pyramids.
   <https://news.liverpool.ac.uk/2018/11/02/ancient-quarry-ramp-system-may-have-helped-workers-build-egypts-great-pyramids/>`__

.. [#] `EarthbagBuilding.com <https://www.earthbagbuilding.com/>`__

.. [#] `機種選定の為の引張力の計算方法 <https://www.maxpull.co.jp/wp_maxpull/wp-content/uploads/2018/03/inchoryokukeisan.pdf>`__
